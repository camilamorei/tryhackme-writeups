# Windows Threat Detection 2 - Ingress Tool Transfer

## Overview

This room explores ingress tool transfer, a technique attackers use to download files and tools onto a compromised system. It focuses on identifying suspicious downloads and understanding how different utilities can be abused to transfer potentially malicious files.

## Topics Covered

- Ingress Tool Transfer
- Browser-based downloads
- File transfers using `curl.exe`
- Abuse of `certutil.exe`
- File downloads using PowerShell `Invoke-WebRequest`
- Windows threat detection and suspicious download activity

## Methods Investigated

### 1. Web Browser

A file is downloaded by navigating to a URL in Google Chrome. Browser activity can provide useful evidence when investigating suspicious downloads.

### 2. curl.exe

The `curl.exe` utility can download files from remote servers. Analysts should investigate command-line arguments, URLs, and the files created during the transfer.

### 3. certutil.exe

Although `certutil.exe` is a legitimate Windows certificate utility, attackers may abuse it to download files. Unexpected network activity involving this executable can be a useful detection indicator.

### 4. PowerShell Invoke-WebRequest

PowerShell's `Invoke-WebRequest` command can retrieve content from remote URLs. Suspicious commands and unexpected downloads may indicate malicious activity.

## Detection Considerations

When investigating possible ingress tool transfer, examine:

- Process creation and command-line arguments
- Network connections and requested URLs
- Files created or downloaded on the endpoint
- Parent-child process relationships
- Browser download history
- PowerShell execution logs
- Unexpected use of legitimate Windows utilities

## Key Takeaways

Legitimate applications and built-in Windows utilities can be abused to download malicious files. Effective detection requires correlating process execution, network activity, file creation, and command-line evidence rather than relying on executable names alone.

## Tools and Technologies

- Windows
- Google Chrome
- curl.exe
- certutil.exe
- PowerShell
- Windows event logs

## Room

TryHackMe: Windows Threat Detection 2

Topic: Ingress Tool Transfer
