# Detecting AD Credential Attacks

## Overview

This room focuses on detecting credential-based attacks against Active Directory environments using Splunk and Windows event logs. It explores common techniques used by attackers to obtain, extract, and abuse domain credentials.

The investigation uses security events and Sysmon telemetry to identify suspicious activity and understand how different attack techniques appear in logs.

## Objectives

- Understand common Active Directory credential attacks.
- Identify Kerberoasting and AS-REP Roasting attempts.
- Detect processes accessing LSASS memory.
- Investigate suspicious Active Directory replication activity.
- Identify attempts to extract the NTDS.dit database.
- Analyze Windows event logs and Sysmon events using Splunk.

## Topics Covered

### Kerberoasting

Kerberoasting targets service accounts associated with Service Principal Names (SPNs). Attackers request service tickets and attempt to crack their encrypted portions offline.

Detection involves analyzing Kerberos service ticket requests, particularly Event ID 4769, and looking for unusual request patterns or weak encryption types such as RC4.

### AS-REP Roasting

AS-REP Roasting targets domain accounts that do not require Kerberos pre-authentication.

Attackers can request authentication responses for these accounts and attempt to crack the encrypted data offline.

Event ID 4768 can help identify suspicious authentication requests. A pre-authentication type of 0 may indicate an account configured without pre-authentication.

### LSASS Credential Dumping

LSASS (Local Security Authority Subsystem Service) manages authentication on Windows systems and may contain sensitive credential information in memory.

Attackers may attempt to access its memory to extract credentials.

Sysmon Event ID 10 records process access activity and can help identify suspicious processes interacting with lsass.exe.

Important fields include SourceImage, TargetImage, GrantedAccess, and CallTrace.

### DCSync

DCSync abuses Active Directory replication mechanisms to request credential data from a domain controller.

Attackers with sufficient replication permissions can impersonate a domain controller and retrieve password hashes.

Event ID 4662 can help identify suspicious directory access operations. Investigators should examine replication-related permissions and correlate Logon IDs with authentication events to identify the source of the activity.

### NTDS.dit Extraction

NTDS.dit is the Active Directory database that stores information about domain accounts, including password hashes.

Attackers may use tools such as ntdsutil.exe or Volume Shadow Copy techniques to obtain a copy of this database.

Detection involves monitoring process creation and file activity through Sysmon events, especially Event IDs 1 and 11.

Suspicious command-line arguments, shadow copy operations, and unexpected database copies may indicate an attempt to extract Active Directory credentials.

## Key Takeaways

- Kerberoasting and AS-REP Roasting abuse weaknesses in Kerberos authentication.
- LSASS memory access can expose credentials stored on Windows systems.
- DCSync abuses Active Directory replication permissions to retrieve credential data.
- NTDS.dit extraction can expose password hashes for domain accounts.
- Windows Security logs and Sysmon provide valuable telemetry for detecting credential attacks.
- Correlating multiple events helps analysts understand the sequence and origin of suspicious activity.

## Conclusion

This room demonstrates how attackers target Active Directory credentials through different techniques and how defenders can detect these activities using Splunk.

Understanding Windows authentication events, Sysmon telemetry, and Active Directory replication behavior is essential for investigating credential-based attacks and improving domain security.
