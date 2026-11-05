# M365 Monitoring Basics

## Overview

This room covers Microsoft 365 security monitoring and incident investigation using Splunk. It focuses on identifying compromised accounts, analyzing Entra ID sign-in activity, investigating audit logs, and detecting suspicious actions across Microsoft 365 services.

## Topics Covered

- Microsoft Entra ID
- Identity Providers (IdP)
- Multi-Factor Authentication (MFA)
- Entra ID Sign-In Logs
- Entra ID Audit Logs
- Microsoft 365 Unified Audit Logs
- Splunk queries
- Post-compromise activity investigation

## Task 2: What Are Identity Providers

Entra ID is a cloud-based Identity Provider (IdP) used to manage identities and authentication.

A server account is classified as a device identity.

## Task 3: Identities as the Target

Multi-Factor Authentication (MFA) adds an additional authentication requirement, preventing attackers from accessing accounts using only stolen passwords.

Identity logs help security analysts monitor authentication activity and detect suspicious behavior.

## Task 4: Entra ID Sign-In Logs

Entra ID sign-in logs provide information about authentication attempts, including successful and failed sign-ins, IP addresses, applications, and error codes.

Basic query:

```spl
index=scenario sourcetype="azure:aad:signin"
```

Useful fields:

- userPrincipalName
- ipAddress
- appDisplayName
- status.errorCode

Investigation results:

- Compromised account: allan.smith@finegalo.thm
- Attacker IP: 2804:2488:7082:a4c0:fd97:b11b:9895:49c0
- Location: Belo Horizonte
- First successful sign-in: 2/11/26 6:16:53.000 PM
- First application after OfficeHome: One Outlook Web

## Task 5: Entra ID Audit Logs

Entra ID Audit Logs record administrative actions and changes made to identities and resources.

Basic query:

```spl
index=scenario sourcetype="azure:aad:audit"
```

To investigate changes targeting a specific user:

```spl
index=scenario sourcetype="azure:aad:audit" targetResources{}.userPrincipalName="allan.smith@finegalo.thm"
| eval initiator=coalesce('initiatedBy.user.userPrincipalName', 'initiatedBy.app.displayName')
| sort - _time
| table _time, initiator, activityDisplayName, result, targetResources{}.userPrincipalName
```

Important fields:

- activityDisplayName: Action performed.
- initiatedBy: User or application that initiated the action.
- targetResources: Resource or identity affected by the action.
- modifiedProperties: Properties changed during the activity.

Investigation results:

- First change: User started security info registration
- Activity revealing modified properties: Update user
- Second change: Reset password (self-service)

## Task 7: M365 Audit Logs

Microsoft 365 Unified Audit Logs record activities performed across services such as Exchange, SharePoint, and OneDrive.

Basic query:

```spl
index="scenario" sourcetype="o365:management:activity"
```

Useful fields:

- Operation: Action performed.
- UserId: Account responsible for the action.
- ClientIP: Source IP address.
- Workload: Microsoft 365 service involved.
- ObjectId: Resource affected by the action.

To investigate activities performed by a compromised account:

```spl
index="scenario" sourcetype="o365:management:activity" UserId="allan.smith@finegalo.thm"
| sort - _time
| eval sourceIP=coalesce('ClientIP', 'ClientIPAddress')
| table _time, Operation, UserId, sourceIP, Workload, ObjectId
```

Investigation results:

- Application used: Exchange
- Operation: New-InboxRule
- Email subject: URGENT: Approval for new internal VPN Access
- Response access time: 2/11/26 6:20:09.000 PM
- Response storage path: \Deleted Items

## Key Takeaways

- Entra ID provides identity and authentication management.
- Sign-in logs help identify suspicious authentication attempts.
- Audit logs reveal changes made to accounts and other resources.
- M365 audit logs provide visibility into activities across cloud services.
- Splunk can correlate identity and application activity to investigate post-compromise behavior.

## Conclusion

This room demonstrated how to investigate suspicious Microsoft 365 activity using Splunk. By analyzing Entra ID Sign-In Logs, Entra ID Audit Logs, and Microsoft 365 Unified Audit Logs, security analysts can identify compromised accounts, trace attacker actions, and investigate post-compromise activity.
