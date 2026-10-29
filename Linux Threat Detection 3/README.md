# Linux Threat Detection 3

## Overview

This room focuses on detecting advanced Linux threats and targeted attacks. It explores reverse shells, privilege escalation, and persistence techniques used by attackers to maintain access to compromised systems.

The exercises use Linux audit logs and authentication logs to reconstruct attack chains and identify suspicious activity.

## Learning Objectives

- Understand how reverse shells are established and detected.
- Investigate privilege escalation attempts and identify changes in user privileges.
- Detect persistence through cron jobs and systemd services.
- Identify unauthorized user accounts and SSH key modifications.
- Understand how compromised Linux systems can become entry points for larger attacks.

## Topics Covered

### 1. Reverse Shell Detection

Reverse shells allow attackers to obtain an interactive session by connecting from a compromised machine to an attacker-controlled host.

Detection techniques include:

- Searching audit logs for suspicious processes such as `socat`.
- Identifying parent and child processes.
- Tracing commands back to vulnerable applications.
- Investigating suspicious outbound connections.

Useful commands:

```bash
ausearch -i -x socat
ausearch -i --pid <PID>
ausearch -i --ppid <PPID>
```

### 2. Privilege Escalation

Privilege escalation occurs when an attacker gains permissions beyond their initial access level.

Detection focuses on:

- Unusual discovery commands.
- Suspicious downloads and executable files in temporary directories.
- Exploit execution.
- Changes in effective user privileges.
- Attempts to access sensitive files or transfer data.

Useful commands:

```bash
ausearch -i -if /home/ubuntu/scenario/audit.log
ausearch -i -x <COMMAND>
ausearch -i --ppid <PID>
```

### 3. Startup Persistence

Attackers may configure malware to execute automatically after a reboot or at scheduled intervals.

Common persistence mechanisms include:

- Cron jobs.
- Systemd services.

Important locations to monitor:

```text
/etc/crontab
/etc/cron.d/
/var/spool/cron/
/var/spool/crontab/
/lib/systemd/system/
/etc/systemd/system/
```

Useful investigation commands:

```bash
ausearch -i -f /etc/systemd
ausearch -i -x crontab
systemctl list-units --type=service
```

### 4. Account Persistence

Attackers may create additional accounts or modify SSH authentication files to preserve access.

Important indicators include:

- Unexpected user creation.
- Unauthorized membership in privileged groups.
- Changes to SSH authorized keys.
- Suspicious authentication events.

Useful commands:

```bash
grep -E 'useradd|usermod' /var/log/auth.log
ausearch -i -f /root/.ssh/authorized_keys
```

### 5. Targeted Linux Attacks

Linux servers can be targets of espionage, ransomware, and other advanced intrusions. A compromised server may also provide an entry point into a larger corporate network.

Effective detection requires correlating multiple events rather than investigating individual commands in isolation.

## Key Takeaways

- Audit logs help reconstruct process execution and identify the origin of suspicious activity.
- Parent-child process relationships are essential for investigating attack chains.
- Comparing user privileges before and after suspicious execution helps identify privilege escalation.
- Cron jobs, systemd services, user accounts, and SSH keys are important persistence indicators.
- Linux security monitoring is essential even in environments primarily based on Windows.
- Correlating host and authentication logs improves threat detection.

## Tools and Technologies

- Linux
- Bash
- auditd
- ausearch
- systemd
- cron
- SSH
- Linux authentication logs
- MITRE ATT&CK

## Conclusion

This room demonstrates how to investigate targeted Linux attacks by tracing reverse shells, identifying privilege escalation, and detecting persistence mechanisms. These techniques are valuable for blue team operations, incident response, and security monitoring.
