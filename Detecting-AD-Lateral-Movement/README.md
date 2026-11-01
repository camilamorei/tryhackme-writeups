# Detecting AD Lateral Movement

## Overview

This room explores how attackers move laterally through Active Directory environments after compromising an initial account or workstation.

It focuses on detecting lateral movement through SMB, PsExec, and RDP by analyzing Windows Event Logs and identifying suspicious authentication activity, remote commands, and connections between machines.

## Task 2: Discovery and Reconnaissance

Attackers often begin by gathering information about the Active Directory environment.

This includes identifying domain controllers, domain trusts, users, groups, and computers.

The first discovery command executed was:

```cmd
nltest /domain_trusts
```

The PowerShell command used to enumerate domain users was:

```powershell
Import-Module ActiveDirectory; Get-ADUser -Filter * -Properties MemberOf | Select-Object Name, SamAccountName
```

Important events to monitor:

- Sysmon Event ID 1: Process creation.
- PowerShell Event ID 4104: Script block logging.

## Task 3: How Lateral Movement Works

Lateral movement allows attackers to move from one compromised machine to another using available credentials and legitimate administrative protocols.

Important Windows Event IDs:

- Event ID 4624: Successful logon.
- Event ID 4648: Logon attempt using explicit credentials.

Logon Types:

- Type 3: Network logon.
- Type 7: Unlock.
- Type 10: Remote Interactive logon, commonly associated with RDP.

A Logon Type 10 indicates an RDP session.

## Task 4: Detecting SMB Lateral Movement

SMB (Server Message Block) is a protocol commonly used for file sharing and remote administration.

It typically operates over TCP port 445.

Administrative shares include:

- ADMIN$
- C$
- IPC$

Important Event IDs:

- Event ID 5140: A network share was accessed.
- Event ID 5145: A network share object was checked to see whether the client can be granted access.

Investigation findings:

- Account used to access ADMIN$: `luke.sullivan`
- User responsible for executing the lateral movement commands: `michelle.smith`

This demonstrates why it is important to distinguish between the account used for authentication and the account responsible for launching commands.

## Task 5: Detecting PsExec Lateral Movement

PsExec is a legitimate Microsoft Sysinternals utility that allows administrators to execute processes remotely. Attackers can abuse it to move laterally across a network.

PsExec commonly uses SMB and administrative shares to transfer and execute files on remote systems.

Important artifacts:

- Event ID 7045: A new service was installed.
- Sysmon Event ID 17: Named pipe created.
- Sysmon Event ID 1: Process creation.
- Event ID 5145: Detailed file share access.

Investigation findings:

Destination host:

```text
THM-SQL-SRV
```

First command executed from the source machine:

```text
C:\Tools\PsExec.exe  -accepteula \\THM-SQL-SRV cmd /c "hostname & whoami & ipconfig"
```

Note: There are two spaces between `PsExec.exe` and `-accepteula`. This whitespace is important when submitting the answer.

## Task 6: Detecting RDP Lateral Movement

Remote Desktop Protocol (RDP) allows users to connect to and control remote Windows machines.

It commonly operates over TCP port 3389.

The most important event for detecting successful RDP logons is Event ID 4624 with Logon Type 10.

When investigating RDP lateral movement, it is important to identify:

- The source IP address.
- The destination machine.
- The account used.
- The Logon ID.
- Previous RDP connections that may reveal the original source of the attack.

Investigation findings:

Source IP of the RDP session that reached the Domain Controller:

```text
10.5.30.120
```

Original source IP of the RDP chain:

```text
10.5.50.12
```

## Task 7: Investigating the Challenge

This task involves correlating Windows events in Splunk to investigate suspicious service installation and lateral movement activity.

The investigation focuses on identifying the service binary, account used to access ADMIN$, source IP, remote command, and originating host.

Investigation findings:

Service binary path:

```text
%SystemRoot%\svcupdate.exe
```

Account used to access ADMIN$:

```text
ryan.chen
```

Source IP address:

```text
10.5.50.15
```

First remote command executed:

```cmd
"cmd" /c "hostname & whoami & ipconfig"
```

Originating host:

```text
THM-HR-WS
```

## Key Takeaways

- Active Directory enumeration helps attackers understand the domain environment.
- SMB can be abused to access administrative shares and move between machines.
- PsExec enables remote command execution and may leave service installation artifacts.
- RDP activity can be identified through successful logon events with Logon Type 10.
- Event IDs 4624, 4648, 5140, 5145, and 7045 are useful when investigating lateral movement.
- Correlating source IPs, destination hosts, usernames, process creation, and logon events helps reconstruct an attack chain.

## Conclusion

This room demonstrates how attackers can abuse legitimate Windows protocols and administrative tools to move across an Active Directory environment.

For defenders, detecting lateral movement requires more than identifying individual events. Correlating authentication logs, network share access, process creation, service installation, and remote sessions provides a clearer picture of the attack.
