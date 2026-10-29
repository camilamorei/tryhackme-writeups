# Windows Threat Detection 3

## Overview

This room focuses on the final stages of the Windows threat detection journey, covering Command and Control (C2), Persistence, and Impact. It explores how attackers maintain control of compromised systems, establish long-term access, and prepare infected hosts for further malicious activities.

## Topics Covered

- Command and Control (C2)
- Windows persistence techniques
- Backdoor user accounts
- Windows services and scheduled tasks
- Startup folder persistence
- Registry Run key persistence
- Windows Security and Sysmon event logs
- Ransomware and its impact on corporate networks
- MITRE ATT&CK tactics and techniques

## Tasks and Investigations

### Task 2: Command and Control

Investigated Sysmon logs to identify a suspicious downloaded archive, locate hidden C2 malware, and determine the domain used for command and control communications.

### Task 3: Persistence Overview

Analyzed Windows Security logs to investigate failed login attempts, identify a backdoor account, and determine which privileged group the account was added to.

### Task 4: Persistence - Tasks and Services

Investigated Windows Security and Sysmon logs to identify persistence mechanisms involving Windows services and scheduled tasks. Examined how malicious programs can be configured to execute after system startup.

### Task 5: Persistence - Run Keys and Startup

Investigated persistence through the Windows Startup folder and registry Run keys. Examined process relationships and malware execution output to identify suspicious activity.

### Task 6: Impact and Threat Detection Recap

Reviewed the impact of persistent threats on corporate Windows environments, including botnets, espionage, network compromise, and ransomware. Revisited the importance of detecting attacks as early as possible.

## Windows Event IDs

| Event ID | Description |
|---|---|
| 1 (Sysmon) | Process creation |
| 11 (Sysmon) | File creation |
| 13 (Sysmon) | Registry value modification |
| 4720 (Security) | User account created |
| 4724 (Security) | Attempt to reset an account password |
| 4732 (Security) | Member added to a security-enabled local group |
| 4697 (Security) | Service installed |
| 4698 (Security) | Scheduled task created |
| 7045 (System) | New service installed |

## Key Takeaways

- C2 channels allow attackers to remotely control compromised hosts.
- Backdoor accounts can provide unauthorized access and elevated privileges.
- Services and scheduled tasks can execute malware automatically.
- Startup folders and registry Run keys can maintain persistence across user logins.
- Sysmon and Windows event logs provide valuable evidence for threat investigations.
- Ransomware can cause severe operational and financial damage.
- Early detection, particularly during Initial Access, can prevent an attack from progressing into more damaging stages.

## Tools and Technologies

- Windows Event Viewer
- Sysmon
- Windows Security logs
- Windows Registry
- Windows Services
- Task Scheduler
- MITRE ATT&CK

## Room Information

Platform: TryHackMe

Room: Windows Threat Detection 3

Focus: Command and Control, Persistence, and Impact
