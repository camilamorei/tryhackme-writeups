# TryHackMe: Blue

## Overview

Blue is a beginner-friendly room focused on identifying and exploiting the MS17-010 vulnerability, also known as EternalBlue, on a Windows machine.

## Tasks

### Task 1: Recon

- Scanned the target using Nmap.
- Identified 3 open ports with port numbers under 1000.
- Identified the MS17-010 vulnerability.

### Task 2: Gain Access

- Selected the EternalBlue Metasploit module.
- Exploitation module: `exploit/windows/smb/ms17_010_eternalblue`
- Required option: `RHOSTS`
- Configured the payload `windows/x64/shell/reverse_tcp`.
- Obtained a shell on the target machine.

### Task 3: Escalate

- Used the post module `post/multi/manage/shell_to_meterpreter` to convert the shell into a Meterpreter session.
- Configured the `SESSION` option.
- Used `getsystem` and `getuid` to check privileges.
- Inspected running processes with `ps` and practiced process migration with `migrate`.

### Task 4: Cracking

- Used `hashdump` to retrieve Windows password hashes.
- Identified the non-default user as `Jon`.
- Cracked the user's password during the lab.

### Task 5: Find Flags

- Located the flags in key Windows system locations.
- Practiced searching for files using Meterpreter.
- Explored important directories, including the Windows system root, configuration directory, and user documents.

## Tools Used

- Nmap
- Metasploit Framework
- Meterpreter
- John the Ripper
- Windows command shell

## Key Takeaways

- Nmap helps identify open ports and services.
- MS17-010 is a critical SMB vulnerability associated with EternalBlue.
- Metasploit provides modules for exploitation and post-exploitation.
- Meterpreter supports privilege checks, process inspection, and file searching.
- Password hashes can be analyzed with password-cracking tools in authorized lab environments.

## Disclaimer

All activities were performed for educational purposes within the TryHackMe lab environment. Only test systems for which you have explicit authorization.

## Platform

[TryHackMe](https://tryhackme.com/room/blue)
