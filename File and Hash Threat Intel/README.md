# File and Hash Threat Intel

## Overview

This room explores how security analysts use file and hash intelligence to investigate suspicious binaries, enrich security alerts, and determine whether files are benign or malicious.

It covers filename and filepath heuristics, hash lookups, malware intelligence platforms, sandbox analysis, and MITRE ATT&CK technique mapping.

## Learning Objectives

- Identify suspicious filenames and filepaths using common heuristics.
- Use file hashes to investigate suspicious binaries.
- Understand how VirusTotal and MalwareBazaar support threat intelligence.
- Interpret sandbox reports and extract indicators of compromise.
- Identify malware behavior and map observed techniques to MITRE ATT&CK.

## Topics Covered

### Filename and Filepath Analysis

Filepaths and filenames provide initial clues during malware triage. Suspicious indicators include double extensions, system binary impersonation, unusual filenames, and payloads stored in temporary or writable directories.

These indicators do not independently prove that a file is malicious, but they help analysts prioritize investigations.

### File Hash Intelligence

Cryptographic hashes, including SHA256 and MD5, provide fingerprints that help identify files regardless of their filenames.

Hash lookups can reveal detection scores, threat classifications, file properties, submission timestamps, and relationships with other suspicious artifacts.

### Threat Intelligence Platforms

VirusTotal aggregates detection results and file intelligence from multiple security vendors.

MalwareBazaar provides access to malware samples, family classifications, tags, and related threat intelligence that can support investigations and threat hunting.

### Sandbox Analysis

Sandbox environments execute suspicious files in controlled conditions and collect behavioral information.

Analysts can investigate process trees, command-line activity, extracted strings, network indicators, and other behaviors to determine the potential impact of a sample.

### MITRE ATT&CK Mapping

Observed malware behaviors can be mapped to MITRE ATT&CK techniques. This helps analysts communicate adversary activity and develop detection and response strategies.

### Sandbox Limitations

Malware may evade analysis through environment awareness checks, anti-debugging techniques, delayed execution, encrypted traffic, obfuscation, and fileless execution.

Sandbox results should be correlated with additional evidence instead of being treated as definitive on their own.

## Tools and Technologies

- TryDetectThis
- VirusTotal
- MalwareBazaar
- Hybrid Analysis
- Joe Sandbox
- SHA256 and MD5 hashing utilities
- MITRE ATT&CK

## Key Takeaways

- Filename and filepath heuristics provide useful initial investigation clues.
- Hashes allow analysts to identify and research suspicious files.
- Threat intelligence platforms provide detection results, classifications, and contextual information.
- Sandbox reports reveal runtime behavior and help identify indicators of compromise.
- MITRE ATT&CK mapping helps describe observed adversary techniques.
- Effective threat intelligence requires validating evidence and accounting for analysis limitations.

## Conclusion

This room provided practical experience with file and hash threat intelligence, from identifying suspicious artifacts to investigating their metadata, reputation, and runtime behavior. These skills support security alert triage, threat hunting, and incident response.
