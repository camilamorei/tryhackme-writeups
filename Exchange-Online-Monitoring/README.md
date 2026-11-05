# Exchange Online Monitoring

## Task 1 - Introduction

This room explores how attackers abuse Microsoft Exchange Online after compromising a mailbox and how SOC analysts can detect these activities using Splunk.

The main topics covered include:

- Exchange Online logging and monitoring
- Suspicious mailbox rules and email forwarding
- Phishing campaigns launched from compromised mailboxes
- Message trace and unified audit log analysis
- Incident investigation and attack timeline reconstruction

## Task 2 - Exchange Online Overview

Exchange Online is Microsoft's cloud-based email and calendaring service, part of Microsoft 365.

A typical Exchange Online compromise follows these stages:

1. Credential Theft - Obtaining valid user credentials through phishing, credential stuffing, or stolen credentials.
2. Initial Access - Authenticating to Microsoft 365 using compromised credentials.
3. Discovery - Reading emails and gathering sensitive information.
4. Persistence - Creating inbox rules, configuring email forwarding, or adding mailbox delegates.
5. Lateral Movement - Using the compromised account to send phishing emails to other employees.

**Answer:**

- Attack stage involving phishing emails sent from a compromised account: Lateral Movement.

## Task 3 - Exchange Online Logging

Three main log sources are used to investigate Exchange Online compromises.

### Exchange Online Sign-In Logs

These logs record authentication attempts, including the user, IP address, location, and authentication status.

```spl
index=* sourcetype="azure:aad:signin" appDisplayName="One Outlook Web"
| table _time userPrincipalName appDisplayName ipAddress location.city status.errorCode
| sort - _time
```

### Microsoft 365 Unified Audit Logs

These logs record activities performed inside Exchange Online.

```spl
index=* sourcetype="o365:management:activity" Workload=Exchange
| table _time UserId Operation Workload
```

Important operations:

| Operation | Description |
|---|---|
| MailItemsAccessed | Emails accessed or read |
| Send | Email sent from a mailbox |
| New-InboxRule | New inbox rule created |
| Set-InboxRule | Existing inbox rule modified |
| Set-Mailbox | Mailbox settings changed |
| Add-MailboxPermission | Delegate access granted |

### Message Trace Logs

Message trace records the delivery journey of emails, including sender, recipient, subject, delivery status, and timestamp.

```spl
index=* sourcetype="o365:reporting:messagetrace"
| table Received SenderAddress RecipientAddress Subject Status FromIP
```

**Answers:**

- Exchange Online application name: `One Outlook Web`
- Feature abused to automatically delete phishing replies: Inbox Rules.

## Task 4 - Detecting Mailbox Rule Abuse

Attackers can abuse inbox rules, mailbox-level forwarding, and delegate permissions to maintain persistence and hide their activities.

### Inbox Rule Creation

```spl
index=task4_5 Workload=Exchange Operation=New-InboxRule
| table _time UserId Name DeleteMessage ForwardTo SubjectContainsWords
```

Important fields:

- `Name`: Name of the inbox rule.
- `SubjectContainsWords`: Words that trigger the rule.
- `DeleteMessage`: Indicates whether matching emails are deleted.
- `ForwardTo`: Destination address for forwarded emails.

A particularly suspicious indicator is `DeleteMessage=True`, which may indicate that the attacker is deleting replies to phishing emails.

### Mailbox-Level Forwarding

```spl
index=task4_5 Workload=Exchange Operation=Set-Mailbox
| table _time UserId ForwardingSmtpAddress DeliverToMailboxAndForward
```

Important indicators include external forwarding addresses and `DeliverToMailboxAndForward=False`.

### Answers

- Suspicious forwarding rule: `Cleanup`
- Trigger word: `Verify`
- External forwarding address: `d4ruy6g@protonmail.com`

## Task 5 - Detecting Phishing from Compromised Mailbox

A compromised mailbox can be used to send convincing phishing emails to other employees.

### MailItemsAccessed

This operation records when emails are accessed or read.

```spl
index=task4_5 Workload=Exchange Operation=MailItemsAccessed
| table _time UserId ClientIPAddress OperationCount
```

Suspicious indicators:

- Access from unusual IP addresses.
- High `OperationCount` values.
- Access outside normal business hours.

### Send Operation

The `Send` operation records emails sent from a mailbox.

```spl
index=task4_5 Workload=Exchange Operation=Send
| table _time UserId Item.Subject ClientIP SaveToSentItems
```

Important fields:

- `UserId`: Account that sent the email.
- `Item.Subject`: Email subject.
- `ClientIP`: Source IP address.
- `SaveToSentItems`: Indicates whether the email was saved in Sent Items.

`SaveToSentItems=False` can indicate an attempt to hide phishing activity.

### Message Trace Investigation

```spl
index=task4_5 sourcetype="o365:reporting:messagetrace"
| table Received SenderAddress RecipientAddress Subject Status FromIP
```

Message trace helps identify recipients and determine whether suspicious emails were successfully delivered.

### Answers

- Phishing email subject: `Urgent: Verify Your Account`
- Number of recipients: `2`
- Sending IP address: `190.2.149.93`

## Task 6 - Incident Investigation

This task involves investigating a compromised Exchange Online mailbox belonging to Robert Green, Finance Manager at TechCorp.

The investigation uses the `task6` index and focuses on identifying the attacker's activities and reconstructing the incident timeline.

### Sign-In Investigation

```spl
index=task6 sourcetype="azure:aad:signin"
| table _time userPrincipalName ipAddress location.city status.errorCode
| sort - _time
```

### Inbox Rule Investigation

```spl
index=task6 Workload=Exchange Operation=New-InboxRule
| table _time UserId Name DeleteMessage ForwardTo SubjectContainsWords
| sort - _time
```

### Mailbox Forwarding Investigation

```spl
index=task6 Workload=Exchange Operation=Set-Mailbox
| table _time UserId ForwardingSmtpAddress DeliverToMailboxAndForward
| sort - _time
```

### Phishing Email Investigation

```spl
index=task6 Workload=Exchange Operation=Send
| table _time UserId Item.Subject ClientIP SaveToSentItems
| sort - _time
```

### Message Trace Investigation

```spl
index=task6 sourcetype="o365:reporting:messagetrace"
| table Received SenderAddress RecipientAddress Subject Status FromIP
| sort - _time
```

### Answers

- Malicious login city: `Ursynow`
- Suspicious inbox rule: `Maintenance`
- External forwarding address: `x7tpq2m@protonmail.com`
- Phishing email subject: `Action Required: Password Reset`
- Phishing email sending IP: `138.199.21.211`
- User who replied: `emma.clarke@techcorp.thm`

## Task 7 - Conclusion

This room demonstrated how attackers abuse Exchange Online after compromising a mailbox and how SOC analysts can investigate these activities using Splunk.

Key concepts learned:

- Identifying suspicious authentication activity through Entra ID sign-in logs.
- Investigating mailbox access through unified audit logs.
- Detecting malicious inbox rules and unauthorized email forwarding.
- Identifying phishing campaigns through the `Send` operation.
- Using message trace to identify recipients and confirm email delivery.
- Reconstructing attack timelines using multiple log sources.
- Understanding persistence techniques involving mailbox permissions and forwarding configurations.

The investigation highlights the importance of correlating authentication logs, audit events, and message trace data to understand the full scope of an Exchange Online compromise.
