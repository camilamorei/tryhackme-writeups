# Phishing Prevention

## Overview

This room explores the security controls and techniques used to prevent, detect, and mitigate phishing attacks. It covers email authentication protocols, SMTP traffic analysis, email attachment inspection, and organizational anti-phishing defenses.

## Learning Objectives

- Understand SPF, DKIM, DMARC, and S/MIME.
- Analyze SMTP response codes and network traffic using Wireshark.
- Inspect email headers, message contents, and attachments.
- Understand technical controls used to detect and prevent phishing attacks.
- Learn how sandboxing helps analyze suspicious files safely.

## Topics Covered

### Sender Policy Framework (SPF)

SPF uses DNS TXT records to specify which mail servers are authorized to send email on behalf of a domain. Receiving servers check the sender's IP address against the domain's SPF record.

### DomainKeys Identified Mail (DKIM)

DKIM uses cryptographic signatures to verify email authenticity and detect modifications to messages. The recipient's mail server checks the signature using a public key published in DNS.

### Domain-Based Message Authentication, Reporting, and Conformance (DMARC)

DMARC uses SPF and DKIM results, along with domain alignment, to determine how receiving mail servers should handle unauthenticated messages. Its policies include `none`, `quarantine`, and `reject`.

### Secure/Multipurpose Internet Mail Extensions (S/MIME)

S/MIME provides email encryption and digital signatures. Encryption protects message confidentiality, while digital signatures support authentication, integrity, and non-repudiation.

### SMTP Traffic Analysis

Wireshark can be used to inspect SMTP traffic, filter response codes, and investigate email delivery failures.

Useful display filter:

```text
smtp.response.code
```

### Email and Attachment Analysis

Email traffic can reveal sender and recipient information, attachment filenames, encoding methods, and delivery errors. Potentially malicious attachments should be analyzed in a controlled environment.

### Phishing Prevention Techniques

Organizations can reduce phishing risks through email filtering, secure email gateways, link rewriting, sandboxing, warning indicators, phishing reporting tools, and user awareness training.

## Key Takeaways

- SPF verifies whether a sending server is authorized to send email for a domain.
- DKIM uses digital signatures to help verify message authenticity and integrity.
- DMARC defines how receiving servers handle messages that fail authentication and alignment checks.
- S/MIME provides encryption and digital signatures for email communication.
- Wireshark helps investigate SMTP responses and suspicious email traffic.
- Sandboxing allows suspicious files to be examined in an isolated environment.

## Tools Used

- Wireshark
- Google Admin Toolbox Messageheader
- SPF Surveyor
- DKIM record inspection tools
- DMARC domain checkers

## Conclusion

This room demonstrates how email authentication, SMTP traffic analysis, attachment inspection, and organizational security controls work together to reduce phishing risks. Understanding these techniques helps security analysts investigate suspicious messages and strengthen email defenses.
