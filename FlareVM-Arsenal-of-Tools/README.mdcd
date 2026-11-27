FlareVM: Arsenal of Tools
Overview
FlareVM is a customized Windows environment designed for malware analysis, reverse engineering, digital forensics, and incident response.

This room explores tools used to investigate suspicious executables, inspect running processes, analyze file properties, and identify potentially malicious network activity.
Learning Objectives
- Explore the tools included in FlareVM.
- Understand static and dynamic analysis.
- Investigate running processes and parent-child relationships.
- Examine executable files and their properties.
- Analyze suspicious network connections.
Task 1: Introduction
FlareVM stands for Forensics, Logic Analysis, and Reverse Engineering. It provides a collection of tools for malware analysis and digital forensic investigations.
Task 2: Arsenal of Tools
Reverse Engineering
- Ghidra
- x64dbg
- OllyDbg
- Radare2
- Binary Ninja
File Analysis
- CFF Explorer
- PEview
- PEStudio
- HxD
- Detect It Easy
Process Monitoring
- Process Explorer
- Process Monitor
- Autoruns
Digital Forensics
- FTK Imager
- Volatility
- Rekall
Network Analysis
- Wireshark
- Nmap
- Netcat
Task 3: Investigation Tools
Process Monitor
Process Monitor records file system, registry, process, and thread activity in real time.
Process Explorer
Process Explorer displays running processes, parent-child relationships, loaded DLLs, and other process information.
HxD
HxD is a hexadecimal editor used to inspect binary files. The DOS header signature commonly found in Windows PE executables is MZ, represented by the hexadecimal bytes 4D 5A.
CFF Explorer
CFF Explorer allows analysts to inspect Portable Executable files, including headers and imported functions.
Wireshark
Wireshark captures and analyzes network traffic, helping investigators identify protocols, addresses, ports, and suspicious communications.
PEStudio
PEStudio performs static analysis of executable files without running them.
FLOSS
FLOSS extracts strings from binaries and attempts to recover obfuscated strings that may reveal URLs, file paths, and configuration data.
Task 3 Answers
1. FLOSS
2. Process Explorer
3. System
4. Procmon
5. PEStudio
6. E9627EBAAC562067759681DCEBA8DDE8D83B1D813AF8181948C549E342F67C0E
7. 102
8. CFF Explorer
9. 646698572AFBBF24F50EC5681FEB2DB7
10. 5A4D
Task 4: Analyzing Malicious Files
PEStudio Analysis
The file windows.exe was examined using PEStudio. Its metadata, entropy, imported functions, and other properties were investigated for suspicious characteristics.

High entropy may indicate compressed or encrypted data, but it does not independently prove that a file is malicious.
Imported Functions
- set_UseShellExecute: controls whether the operating system shell is used when starting a process.
- RijndaelManaged: provides an implementation of the Rijndael encryption algorithm.
- CryptoStream: supports cryptographic data processing.
- CipherMode: specifies a symmetric encryption mode.
- CreateDecryptor: creates a decryptor for a cryptographic algorithm.
FLOSS Analysis
FLOSS was used to extract strings from windows.exe. This provides additional information that can complement static executable analysis.
Process Explorer Analysis
Process Explorer was used to inspect cobaltstrike.exe. When launched manually in the lab, its observed parent process was explorer.exe.
Process Monitor Analysis
Process Monitor was filtered to investigate activity associated with cobaltstrike.exe.

Destination IP: 47.120.46.210

Defanged IP: 47[.]120[.]46[.]210

Destination port: 81
Task 4 Answers
1. 7.999
2. requireAdministrator
3. set_UseShellExecute
4. RijndaelManaged
5. 92EEF189FB188C541CBD83AC8BA4ACF5
6. 47[.]120[.]46[.]210
7. 81
8. explorer.exe
Task 5: Conclusion
This room introduced FlareVM and demonstrated how its tools support malware analysis, reverse engineering, digital forensics, and incident response.

The exercises showed how static analysis, string extraction, process inspection, and network monitoring can be combined to investigate suspicious executables.
Key Takeaways
- Static analysis examines files without executing them.
- Dynamic analysis observes program behavior during execution.
- File hashes help identify and compare samples.
- Imported functions provide clues about program capabilities.
- Process trees reveal relationships between programs.
- Network analysis can reveal potentially malicious communications.
- Findings should be verified using multiple sources of evidence.
Safety Considerations
Malware analysis should only be performed in isolated, controlled environments. Never execute suspicious samples on personal or production systems.
