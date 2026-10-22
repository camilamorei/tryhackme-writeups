# CAPA: The Basics

## Overview

This room introduces CAPA, a tool developed to identify capabilities in executable files. It helps malware analysts understand what a program can do by detecting patterns associated with specific behaviors.

CAPA can identify capabilities related to persistence, anti-analysis, virtual machine detection, network communication, and other malware behaviors.

## Task 2: CAPA Fundamentals

### Command-line options

| Question | Answer |
|---|---|
| Short option for help | `-h` |
| Option for detailed information | `-v` |
| Option for very verbose output | `-vv` |
| PowerShell command to read a file | `Get-Content` |

## Task 3: CAPA Results

### Cryptographic hash

SHA256:

```text
ae7bc6b6f6ecb206a7b957e4bb86e0d11845c5b2d9f7a00a482bef63b567ce4c
```

### MITRE ATT&CK

| Question | Answer |
|---|---|
| Technique identifier | `T1027` |
| Sub-technique identifier | `T1027.005` |

### MAEC concepts

| Behavior | Answer |
|---|---|
| Activating persistence mechanisms | `Launcher` |
| Fetching additional payloads or resources from the internet | `Downloader` |

## Task 4: Malware Behavior Catalogue (MBC)

The Malware Behavior Catalogue (MBC) describes malware objectives and behaviors.

| Question | Answer |
|---|---|
| Catalogue of malware objectives and behaviors | `Malware Behavior Catalogue (MBC)` |
| Field based on ATT&CK tactics | `Objective` |
| Identifier for Create Process | `C0017` |
| Micro-behavior associated with Base64 and XOR | `Encode Data` |
| Behavior that initiates HTTP communications | `HTTP Communication` |

## Task 5: CAPA Rule Namespaces

Namespaces organize CAPA rules according to the behavior they detect.

| Behavior or purpose | Namespace |
|---|---|
| Evasion, obfuscation, packing, and anti-debugging | `anti-analysis` |
| Virtual machine detection | `anti-vm/vm-detection` |
| Persistence mechanisms | `persistence` |
| String encryption, code obfuscation, and packing | `obfuscation` |
| Staging area for rules under development | `nursery` |

## Task 6: CAPA Rules

CAPA rules use features and conditions to identify specific behaviors in a program.

### Rule identification

| Question | Answer |
|---|---|
| Rule for checking an HTTP status code | `check-http-status-code.yml` |
| Capability associated with `reference-anti-vm-strings.yml` | `reference anti-VM strings` |
| Top-level namespace containing the rule named `run PowerShell expression` | `load-code` |
| API ending in `Ex` referenced by the Windows Sandbox registry rule | `RegOpenKeyEx` |

### Understanding rule features

Rules can use strings, API calls, and logical conditions to determine whether a capability is present.

Examples from the room:

- `anti-VM-Strings-targeting-VMWare.yml` looks for strings matching `VMWare` using a case-insensitive regular expression.
- `schedule task via schtasks.yml` checks for process creation behavior and strings associated with `schtasks`, `/create`, or `Register-ScheduledTask`.

These conditions help CAPA associate evidence in a program with a specific capability.

## Task 7: CAPA Web Explorer

CAPA Web Explorer provides a browser-based interface for exploring CAPA results and inspecting the evidence behind matched rules.

### Questions and answers

| Question | Answer |
|---|---|
| Parameter used to output results in JSON format | `-j` |
| Tool for interactively exploring CAPA results in a browser | `CAPA Web Explorer` |
| Feature used to filter options or results | `Global Search Box` |

### Generating JSON output

The room demonstrates using the JSON and very verbose parameters together:

```powershell
capa.bin -j -vv .\cryptbot.bin > cryptbot_vv.json
```

The generated JSON file can then be uploaded into CAPA Web Explorer for easier inspection.

## Key Takeaways

- CAPA automates the identification of capabilities in executable files.
- Verbose output provides additional information about matched rules.
- JSON output makes CAPA results easier to explore with other tools.
- Rules use features and conditions to detect specific program behaviors.
- Namespaces organize rules into behavioral categories.
- CAPA can support malware analysis and incident response by helping analysts understand potentially malicious software.

## Conclusion

Completing CAPA: The Basics provided an introduction to capability-based malware analysis, CAPA rule structures, malware behavior classification, and the use of CAPA Web Explorer to investigate matched rules.

These concepts provide a foundation for further learning in malware analysis, reverse engineering, and cybersecurity.

## References

- [TryHackMe: CAPA The Basics](https://tryhackme.com/)
- [CAPA Web Explorer](https://mandiant.github.io/capa/explorer/#/)
- [CAPA GitHub Repository](https://github.com/mandiant/capa)
