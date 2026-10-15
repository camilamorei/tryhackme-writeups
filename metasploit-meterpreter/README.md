# TryHackMe: Metasploit: Meterpreter

## Overview

This room explores Meterpreter, a Metasploit payload used during penetration testing. It covers Meterpreter's architecture, available payload versions, built-in commands, and post-exploitation capabilities.

## Topics Covered

- Introduction to Meterpreter
- How Meterpreter works
- Staged and stageless Meterpreter payloads
- Meterpreter payloads for different operating systems
- Core Meterpreter commands
- File system and networking commands
- Process management and migration
- System information gathering
- Post-exploitation techniques
- Loading Meterpreter extensions, including Python and Kiwi
- Credential and hash retrieval in a lab environment

## Tasks

### Task 1: Introduction to Meterpreter

Learned how Meterpreter operates as an agent on a target system, communicates with Metasploit, and uses encrypted communication channels. Explored process identification using `getpid` and process listing with `ps`.

### Task 2: Meterpreter Flavors

Explored different Meterpreter payload versions and the differences between staged and inline payloads. Learned how the target operating system, available components, and network connection options influence payload selection.

### Task 3: Meterpreter Commands

Reviewed common Meterpreter commands for interacting with a target system, managing files, inspecting network connections, listing processes, and retrieving system information.

### Task 4: Post-Exploitation with Meterpreter

Explored post-exploitation commands such as `getuid`, `ps`, `migrate`, `hashdump`, `search`, and `shell`. Learned how these commands can help assess privileges, inspect processes, locate files, and interact with the target system.

### Task 5: Post-Exploitation Challenge

Practiced using Meterpreter in the TryHackMe lab environment to gather system information, inspect user accounts, and locate files containing relevant information. Explored loading additional extensions, including Python and Kiwi, to understand the framework's extended capabilities.

## Tools Used

- Metasploit Framework
- Meterpreter
- msfvenom
- Python extension
- Kiwi extension
- SMB
- Linux terminal

## Key Takeaways

- Meterpreter provides an interactive environment for authorized penetration testing.
- Payload selection depends on the target platform and available communication methods.
- Built-in commands help inspect processes, files, network configuration, and system information.
- Post-exploitation activities can help identify privileges and gather information in a controlled lab.
- Additional extensions provide functionality beyond the standard Meterpreter commands.

## Disclaimer

All activities described in this repository are intended for educational purposes within the TryHackMe lab environment. Only test systems for which you have explicit authorization.

