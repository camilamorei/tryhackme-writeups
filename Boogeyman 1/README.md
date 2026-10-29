# Boogeyman 1

## Overview

Boogeyman 1 is a TryHackMe room focused on investigating a phishing incident through digital forensics and incident response techniques.

The investigation begins with a suspicious email sent to an employee of Quick Logistics. By analyzing email headers, an encrypted attachment, and a malicious Windows shortcut file, it is possible to understand how the attack started and identify the techniques used by the attacker.

## Learning Objectives

- Analyze phishing emails and their headers.
- Identify suspicious sender addresses and email relay services.
- Investigate encrypted email attachments.
- Extract information from Windows shortcut files.
- Decode Base64-encoded PowerShell commands.
- Understand how malicious files can initiate an attack.

## Topics Covered

### Email Analysis

- Email sender and recipient identification.
- DKIM-Signature analysis.
- List-Unsubscribe header inspection.
- Third-party email relay identification.
- Investigation of encrypted attachments.

### Malicious Shortcut Analysis

- Windows LNK file analysis.
- Command Line Arguments inspection.
- Base64 payload identification.
- PowerShell command analysis.

## Tools and Technologies

- lnkparse
- Email header analysis
- Base64 decoding
- PowerShell

## Key Takeaways

This room demonstrates how phishing attacks can use legitimate-looking emails and encrypted attachments to deceive victims.

Analyzing email headers helps identify suspicious infrastructure, while examining LNK files can reveal hidden commands and encoded payloads.

Understanding these techniques is important for identifying phishing attempts and investigating suspicious activity during incident response.

## Conclusion

Boogeyman 1 provides practical experience in phishing investigation and digital forensics. It reinforces the importance of examining email metadata, suspicious attachments, and encoded commands when investigating a potential security incident.
