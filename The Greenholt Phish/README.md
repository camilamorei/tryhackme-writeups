# The Greenholt Phish

## Overview

This TryHackMe room focuses on investigating a suspicious email reported by an employee at Greenholt PLC. The investigation involves analyzing email headers, verifying sender information, checking authentication records, and examining a potentially malicious attachment.

## Objectives

- Analyze email headers and identify suspicious indicators.
- Investigate the originating IP address and its owner.
- Examine SPF and DMARC records.
- Calculate the SHA256 hash of an attachment.
- Use VirusTotal to investigate the attachment and identify its actual file type.

## Task 1: A Message That Doesn't Add Up

### Email Analysis

| Question | Answer |
|---|---|
| Transfer Reference Number | `09674321` |
| Sender Display Name | `Mr. James Jackson` |
| Sender Email Address | `info@mutawamarine.com` |
| Reply-To Address | `info.mutawamarine@mail.com` |
| Originating IP Address | `192.119.71.157` |
| Originating IP Owner | `HostPapa` |
| SPF Record | `v=spf1 include:spf.protection.outlook.com -all` |
| DMARC Record | `v=DMARC1; p=quarantine; fo=1` |

### Attachment Analysis

| Question | Answer |
|---|---|
| Attachment Filename | `SWT_#09674321____PDF__.CAB` |
| SHA256 Hash | `2e91c533615a9bb8929ac4bb76707b2444597ce063d84a4b33525e25074fff3f` |
| File Size | `400.26 KB` |
| Actual File Type | `RAR` |

The attachment uses a `.CAB` extension, but its actual file type is a RAR archive. This discrepancy is a suspicious indicator because the file is disguised as a different format.

## Investigation Methodology

### 1. Inspect the Email

Open `challenge.eml` in Thunderbird and examine the sender, recipient, subject, and Reply-To fields. Compare the sender's identity with the address that receives replies.

### 2. Analyze the Message Source

Inspect the raw email source to locate the originating IP address and relevant SMTP headers. The originating IP can be found in the received-header information.

### 3. Investigate the IP Address

Use a WHOIS lookup or an IP intelligence service to identify the organization associated with the originating IP address.

### 4. Check Email Authentication Records

Use DNS lookup tools to inspect the sender domain's SPF and DMARC records.

Example SPF lookup:

```bash
dig +short TXT mutawamarine.com
```

Example DMARC lookup:

```bash
dig +short TXT _dmarc.mutawamarine.com
```

### 5. Calculate the Attachment Hash

After obtaining the attachment in the lab environment, calculate its SHA256 hash:

```bash
sha256sum 'SWT_#09674321____PDF__.CAB'
```

The hash can then be searched on VirusTotal to review the file's reputation, size, and detected file type.

## Indicators of Suspicious Activity

- The sender's identity and reply address differ.
- The message requests an unexpected money transfer.
- The email contains an unsolicited attachment.
- The attachment extension does not match its actual file type.
- The sender infrastructure and authentication records require further investigation.

## Conclusion

This investigation demonstrates how email header analysis, IP intelligence, SPF and DMARC checks, file hashing, and malware intelligence can help identify phishing attempts. The disguised attachment is an important indicator that the email requires careful investigation before any interaction with its contents.

## Tools Used

- Thunderbird
- WHOIS and IP lookup tools
- DNS utilities
- VirusTotal
- Linux terminal
