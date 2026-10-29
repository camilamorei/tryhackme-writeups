# Linux Threat Detection 1

## Overview

This room focuses on detecting Initial Access techniques targeting Linux systems. It explores SSH brute-force attacks, exposed services, application exploitation, and process tree analysis.

## Learning Objectives

- Understand the risks of exposed SSH services.
- Identify brute-force attacks through authentication logs.
- Detect exploitation attempts using application logs.
- Trace suspicious commands to their originating processes.
- Recognize supply chain compromises and other Initial Access techniques.

## Task 2: Initial Access via SSH

SSH is a common entry point for Linux attacks when servers expose weak password-based authentication or compromised private keys.

Authentication logs can be inspected with:

```bash
cat /var/log/auth.log | grep "sshd"
```

Successful SSH logins can be identified using:

```bash
cat /var/log/auth.log | grep -E 'Accepted'
```

Important indicators include repeated failed logins, unexpected source IP addresses, unusual login times, and suspicious authentication methods.

## Task 3: Detecting SSH Attacks

SSH brute-force attacks involve repeated authentication attempts against one or more accounts. Reviewing authentication logs helps identify targeted users, attack timelines, and the source IP addresses involved.

Useful indicators include:

- Multiple failed login attempts.
- Attempts against several usernames.
- Successful logins following repeated failures.
- Root account access from unexpected IP addresses.

## Task 4: Initial Access via Services

Public-facing applications can provide attackers with an entry point when they contain vulnerabilities or fail to validate user input.

Application logs, such as Nginx access logs, can reveal suspicious requests:

```bash
cat /var/log/nginx/access.log
```

Look for unusual URL parameters, operating system commands in user input, unexpected HTTP status codes, and attempts to access sensitive files.

Command injection can allow an attacker to execute operating system commands through a vulnerable application.

## Task 5: Detecting Service Breach

Process tree analysis helps determine how a suspicious command was executed and which application or user initiated it.

Auditd can be used to search for specific command executions:

```bash
ausearch -i -x whoami
```

Inspect a process by its PID:

```bash
ausearch -i --pid <PID>
```

Search for processes launched by a parent process:

```bash
ausearch -i --ppid <PPID> | grep 'proctitle'
```

Tracing parent and child processes can reveal whether a command originated from a web application, a user session, or another service.

## Task 6: Advanced Initial Access

Linux systems can also be compromised through human-led attacks and supply chain compromises.

Examples include:

- Running untrusted scripts downloaded from the internet.
- Installing malicious packages through typosquatting.
- Executing compromised software updates.
- Using a compromised trusted application to execute malicious commands.

Process tree analysis is useful for investigating these scenarios and tracing suspicious activity back to its origin.

## Key Takeaways

- SSH authentication logs help identify brute-force attacks and suspicious logins.
- Public-facing services can expose an entire Linux host to compromise.
- Application logs provide useful evidence of exploitation attempts.
- Auditd supports process investigation and process tree analysis.
- Trusted applications can become attack entry points after a compromise.
- Investigations should correlate logs, processes, source IP addresses, and user activity.

## Tools and Log Sources

- `/var/log/auth.log`
- `/var/log/nginx/access.log`
- `ausearch`
- `auditd`
- Process tree analysis

## Conclusion

Linux threat detection requires correlating authentication events, application activity, and process execution records. By identifying suspicious behavior and tracing its origin, analysts can better understand how an attacker gained initial access to a Linux system.
