# Windows Logging for SOC

## Overview

This room explores Windows logging from a Security Operations Center (SOC) perspective. It covers Security event logs, Sysmon, and PowerShell logging, showing how analysts can investigate suspicious activity and reconstruct an attack by correlating events from different sources.

## Learning Objectives

- Understand Windows event logs and how to read them.
- Investigate successful and failed authentication attempts.
- Identify suspicious user account changes.
- Analyze process creation events using Sysmon.
- Investigate file creation, registry changes, network connections, and DNS queries.
- Understand PowerShell history logging.
- Correlate events using Logon IDs and Process IDs.

## 1. Windows Logging Fundamentals

Windows records system and user activity in event logs. These records help security analysts investigate incidents, hunt for threats, and develop detection rules.

Windows Event Viewer is a built-in tool used to browse, filter, and analyze event logs.

Windows event logs are stored in EVTX format under:

```text
C:\Windows\System32\winevt\Logs
```

Important Event Viewer fields include:

- Event ID: Identifies the type of event.
- Date and Time: Indicates when the event occurred.
- Keywords: May indicate whether an action succeeded or failed.
- Event Details: Contains information about the event, its source, and its context.

Common log categories include Security, System, and Application.

## 2. Security Log: Authentication

Authentication logs help analysts investigate suspicious logins, brute-force attacks, password spraying, and unauthorized remote access.

### Important Event IDs

| Event ID | Description |
|---|---|
| 4624 | Successful logon |
| 4625 | Failed logon |

### Logon Types

- Logon Type 3: Network logon.
- Logon Type 10: Remote Interactive logon, commonly associated with Remote Desktop Protocol (RDP).

### Detecting Suspicious Authentication

When investigating failed logons, look for:

- Repeated failures against a single account.
- Attempts against multiple accounts from the same source.
- Unexpected source IP addresses or workstation names.
- Unusual login activity outside normal working hours.

For successful logons, investigate unexpected source addresses, suspicious RDP sessions, and activity following the login.

The Logon ID is particularly useful because it can connect authentication events with subsequent actions performed during the same session.

## 3. Security Log: User Management

Windows Security logs record account and group changes that may indicate persistence or privilege escalation.

### Important Event IDs

| Event ID | Description |
|---|---|
| 4720 | User account created |
| 4722 | User account enabled |
| 4723 | Attempt to change an account password |
| 4724 | Attempt to reset an account password |
| 4725 | User account disabled |
| 4726 | User account deleted |
| 4732 | Member added to a security-enabled local group |
| 4733 | Member removed from a security-enabled local group |
| 4738 | User account changed |

### Detecting Suspicious Account Changes

Investigate accounts created by unknown users, changes made at unusual times, unexpected password resets, and additions to privileged groups such as Administrators.

Important fields include:

- Subject: The account performing the action.
- Target Account: The account being modified.
- Group Name: The security group affected by the change.
- Logon ID: Helps correlate the action with the session that performed it.

A newly created account added to privileged groups may indicate a backdoor account used to maintain access.

## 4. Sysmon: Process Monitoring

Sysmon is a Windows system monitoring tool from the Microsoft Sysinternals suite. It provides detailed telemetry that helps analysts investigate process execution and other system activity.

### Important Event IDs

| Event ID | Description |
|---|---|
| Security 4688 | Process creation, when the relevant auditing policy is enabled |
| Sysmon 1 | Process creation |

### Analyzing Process Creation

Sysmon Event ID 1 contains information about the launched process, its parent process, user context, and executable metadata.

Important fields include:

- Image: Path of the executable.
- CommandLine: Command-line arguments used to launch the process.
- ProcessId: Identifier of the launched process.
- ParentImage: Executable that started the process.
- ParentProcessId: Identifier of the parent process.
- Hashes: Hash values that can support malware investigation.
- User and Logon ID: Context about the account and session.

### Suspicious Indicators

- Executables launched from unusual directories such as `C:\Temp` or `C:\Users\Public`.
- Randomly named or unexpected executable files.
- Suspicious parent-child process relationships.
- Unusual command-line arguments.
- Hashes associated with known malicious files.

Tracing parent processes can help reconstruct an execution chain and identify how suspicious activity began.

## 5. Sysmon: Files and Network Activity

Sysmon provides additional event types that help analysts understand what a process does after execution.

### Important Event IDs

| Event ID | Description |
|---|---|
| 3 | Network connection |
| 11 | File creation |
| 13 | Registry value set |
| 22 | DNS query |

### Investigating File Activity

File creation events can reveal malware dropped onto a system. Investigate unexpected executables and scripts, especially those created in temporary or public directories.

Registry changes may reveal attempts to modify system configuration or establish persistence.

### Investigating Network Activity

Network connection events can help identify processes communicating with external hosts. DNS query events can reveal domains contacted by suspicious processes.

Look for:

- Unexpected external connections.
- Connections to suspicious IP addresses or ports.
- DNS queries to unusual or potentially malicious domains.
- Files created by suspicious processes.
- Registry changes associated with persistence.

Correlate the Process ID from these events with Sysmon Event ID 1 to identify the executable and user responsible for the activity.

## 6. PowerShell Logging

PowerShell is a legitimate Windows administration tool that can also be abused for reconnaissance, downloading malware, and executing malicious commands.

Sysmon process creation events can show that `powershell.exe` was launched, but they do not necessarily record every command entered during the session.

### PowerShell History

PowerShell commonly stores interactive command history in:

```text
C:\Users\<USER>\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt
```

Each user may have a separate history file.

### Investigating PowerShell Activity

PowerShell history can reveal commands used to:

- Enumerate local users and groups.
- Read sensitive files.
- Download files from remote servers.
- Investigate the system.
- Perform other potentially suspicious actions.

The history file does not record command output and may not contain commands executed through every execution method. It should therefore be treated as one source of evidence rather than a complete record of PowerShell activity.

Other logging methods, such as PowerShell Script Block Logging, transcription, and endpoint monitoring, can provide additional visibility.

## 7. Correlating Events

A key skill in SOC investigations is connecting events from different log sources.

### Logon ID

Use the Logon ID to associate activity with a particular logon session. For example, an authentication event can be connected to subsequent account changes performed during that session.

### Process ID

Use the Process ID to associate Sysmon file, registry, network, or DNS events with the process that generated them.

Combining these identifiers helps analysts reconstruct an attack timeline and determine which account and process were responsible for suspicious activity.

## Key Takeaways

- Windows logs provide valuable evidence for incident response and threat hunting.
- Event IDs 4624 and 4625 are essential for investigating successful and failed logons.
- User management events can reveal backdoor accounts and privilege escalation.
- Sysmon provides detailed process, file, registry, network, and DNS telemetry.
- PowerShell history can reveal commands that are not visible in basic process creation logs.
- Logon IDs and Process IDs help correlate events and reconstruct attack chains.
- Effective investigations require multiple sources of evidence rather than relying on a single event.

## Skills Practiced

- Windows Event Viewer
- Security event log analysis
- Authentication investigation
- User account and group change analysis
- Sysmon process monitoring
- File and registry event analysis
- Network connection and DNS investigation
- PowerShell history analysis
- Event correlation and attack timeline reconstruction

## Conclusion

This room demonstrated how Windows Security logs, Sysmon, and PowerShell history can be used together to investigate suspicious activity. Understanding these log sources and correlating their events is an important foundation for SOC analysis, threat hunting, and digital forensics.
