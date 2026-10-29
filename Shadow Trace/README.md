# Shadow Trace

## Overview

Shadow Trace is a TryHackMe room focused on basic malware analysis and SOC alert investigation. The scenario involves a suspicious executable named `windows-update.exe` found on a user's machine, along with EDR alerts that require investigation.

The objective is to extract indicators of compromise (IOCs), inspect the suspicious binary, and correlate security alerts to identify potentially malicious activity.

## Learning Objectives

- Extract IOCs from suspicious binaries.
- Identify file properties and calculate file hashes.
- Investigate suspicious URLs and domains.
- Understand the role of socket communication libraries.
- Correlate endpoint alerts with potentially malicious behavior.
- Perform basic SOC triage.

## Task 1: Scenario

The investigation begins after a suspicious file is discovered on a user's workstation. The analyst must examine the executable and investigate related endpoint alerts to determine whether the activity is malicious.

## Task 2: File Analysis

The suspicious binary is located at:

```text
C:\Users\DFIRUser\Desktop\windows-update.exe
```

The analysis focuses on identifying the executable's architecture, calculating its SHA-256 hash, extracting URLs and domains, decoding a flag associated with a suspicious domain, and identifying a library related to socket communication.

### Key Concepts

- SHA-256: A cryptographic hash used to identify a file and verify its integrity.
- Indicators of Compromise (IOCs): Artifacts such as hashes, URLs, domains, and filenames that can help identify suspicious activity.
- Static analysis: Examining a file without executing it.
- Socket communication: Network communication that allows applications to exchange data with other systems.

The extracted indicators can be used to support further investigation, threat hunting, and detection.

## Task 3: Alerts Analysis

This task involves reviewing a simulated alert environment and investigating activity associated with `powershell.exe` and `chrome.exe`.

The investigation requires identifying suspicious URLs and determining the filename associated with the Chrome alert.

### Investigation Approach

1. Review each alert and identify the process involved.
2. Inspect URLs and other artifacts associated with the alert.
3. Determine whether the observed activity is consistent with normal behavior.
4. Record relevant IOCs for further investigation.
5. Correlate the findings to build a clearer picture of the incident.

## Key Takeaways

- File hashes provide a reliable way to identify specific files.
- Suspicious URLs and domains can be valuable IOCs.
- Executable metadata and imported libraries can provide clues about a binary's behavior.
- EDR alerts should be investigated in context rather than treated as isolated events.
- Correlating process activity, network indicators, and downloaded files helps analysts understand potential attack chains.

## Tools and Technologies

- TryHackMe lab environment
- Windows executable analysis tools
- SHA-256 hashing
- Endpoint Detection and Response (EDR) alerts
- IOC extraction
- Static malware analysis

## Conclusion

Shadow Trace provides practical experience in suspicious file analysis, IOC extraction, and endpoint alert investigation. These skills are important for SOC analysts and blue team professionals performing initial triage and investigating potentially malicious activity.
