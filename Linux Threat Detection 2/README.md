# Linux Threat Detection 2

## Overview

This room focuses on detecting post-compromise activity on Linux systems. It covers Discovery commands, malware delivery, common attack motivations, and the investigation of a Dota3 cryptominer infection.

## Learning Objectives

- Identify Discovery commands executed by threat actors.
- Understand common attacks targeting Linux servers.
- Detect malware downloads and file transfers.
- Investigate suspicious processes using auditd logs.
- Analyze a cryptominer infection from initial access to execution.

## Task 2: Discovery Overview

After gaining access to a Linux system, attackers often execute commands to learn about the operating system, users, running processes, network configuration, and available resources.

Common Discovery commands include:

```bash
whoami
hostname
id
uname -a
ps aux
ip a
ss -tnlp
systemd-detect-virt
```

Antivirus and EDR process discovery can help identify whether security tools are running on the compromised system.

## Task 3: Detecting Discovery

Auditd records can help identify suspicious command execution and trace commands to their parent processes.

Search for a specific command:

```bash
ausearch -i -x hostname
```

Inspect a process by its PID:

```bash
ausearch -i --pid <PID>
```

Inspect processes launched by a parent process:

```bash
ausearch -i --ppid <PPID>
```

Investigators should examine the process tree and script contents to determine whether the activity is legitimate or malicious.

## Task 4: Motivation for Attacks

Many Linux attacks focus on quick financial or operational gains. Common objectives include:

- Installing cryptominers to abuse CPU or GPU resources.
- Enrolling compromised systems into botnets for activities such as DDoS attacks.
- Using compromised systems as proxies.
- Downloading additional malware or scripts.

### Ingress Tool Transfer

Attackers commonly use built-in utilities to download or transfer files:

```bash
wget <URL>
curl -O <URL>
scp <source> <destination>
```

Useful detection sources include auditd process records, authentication logs, network traffic, file creation events, and antivirus alerts.

## Task 5: Dota3: First Actions

Dota3 is a Linux malware family associated with automated SSH attacks and cryptomining.

The infection chain can include:

1. Scanning for exposed SSH services.
2. Brute-forcing weak passwords, often targeting root.
3. Executing Discovery commands to inspect the victim.
4. Modifying account credentials and SSH authorized keys.
5. Preparing the system for additional malware.

Relevant commands may include:

```bash
cat /proc/cpuinfo
free -m
lscpu
crontab -l
w
uname -m
```

Authentication logs help identify suspicious SSH access, while auditd records help reconstruct the commands executed after access was gained.

## Task 6: Dota3: Miner Setup

After establishing access, attackers may transfer an archive through SCP, extract it into a hidden temporary directory, and execute its contents.

Common indicators include:

- Unexpected archives transferred through SCP.
- Hidden directories created under `/tmp`.
- Suspicious binaries executed with `nohup`.
- Network scanning against internal address ranges.
- High CPU usage caused by cryptocurrency mining.

Example investigation commands:

```bash
ausearch -i -if /home/ubuntu/scenario/audit.log
ausearch -i -x nohup
```

Process execution records can reveal the full command line used to launch the miner and the network ranges targeted by the attacker.

## Key Takeaways

- Discovery commands reveal how attackers inspect compromised Linux systems.
- Process context is essential when distinguishing malicious commands from legitimate administration.
- Ingress Tool Transfer can be detected through process logs, file events, network traffic, and authentication records.
- Dota3 combines SSH brute force, system discovery, persistence, network scanning, and cryptomining.
- Auditd and authentication logs are valuable sources for reconstructing Linux attack timelines.

## Conclusion

Detecting post-compromise activity requires correlating command execution, process relationships, authentication events, and file activity. Understanding these artifacts helps analysts reconstruct an attack and identify its objectives, from initial Discovery to malware execution.

