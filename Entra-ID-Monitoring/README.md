# Entra ID Monitoring

## Overview

This room focuses on common attacks targeting Microsoft Entra ID identities and how to detect them using Splunk. It covers password-based attacks, Conditional Access Policies, Identity Protection, MFA bypass techniques, privilege escalation, persistence, and OAuth application abuse.

## Topics Covered

- Microsoft Entra ID
- Password Spraying
- Brute Force Attacks
- Conditional Access Policies
- Identity Protection
- MFA Fatigue
- SIM Swapping
- Adversary-in-the-Middle (AiTM) Phishing
- Impossible Travel
- Privilege Escalation
- Persistence Mechanisms
- OAuth Application Abuse
- Splunk and SPL Queries

## Task 2: Password-Based Attacks

Password spraying involves trying a small number of common passwords against multiple accounts, while brute force involves trying many passwords against a single account.

Both techniques can be detected through Entra ID Sign-In Logs.

Basic query:
```
index="task-2" sourcetype="azure:aad:signin" "status.errorCode"!=0 conditionalAccessStatus!=success
| table _time, userPrincipalName, appDisplayName, ipAddress, location.countryOrRegion, status.errorCode, status.failureReason
| sort - _time
```

To identify IP addresses responsible for failed sign-in attempts:
```
index="task-2" sourcetype="azure:aad:signin" "status.errorCode"!=0 conditionalAccessStatus!=success
| stats dc(userPrincipalName) as targeted_accounts, count as failures by ipAddress
| sort - failures
```

Investigation results:

- Password spraying IP: 94.20.222.248
- Throttling brute force IP: 38.165.231.218
- Compromised account: [amanda.costa@finegalo.thm](mailto:amanda.costa@finegalo.thm)

## Task 3: Conditional Access Policies and Identity Protection

Conditional Access Policies evaluate sign-in requests and determine whether access should be granted, blocked, or require additional authentication.

Identity Protection analyzes sign-in behavior and user activity to identify potentially compromised accounts.

There are two main risk categories:

- Sign-in Risk: Evaluates the suspiciousness of an individual authentication attempt.
- User Risk: Evaluates the likelihood that an account has been compromised.

Basic query for high-risk sign-ins:
```
index="task-3" sourcetype="azure:aad:signin"
| where riskLevelDuringSignIn="high"
| table _time, userPrincipalName, appDisplayName, ipAddress, location.countryOrRegion, riskLevelDuringSignIn, riskLevelAggregated
| sort - _time
```

Investigation results:

- User at risk: [allan.senna@finegalo.thm](mailto:allan.senna@finegalo.thm)
- Risk type: anonymizedIPAddress
- Conditional Access policy: Block Suspicious Countries
- Blocked IP: 94.20.222.251

## Task 4: MFA Bypass Techniques

Multi-Factor Authentication adds an additional authentication requirement beyond a password. However, attackers use different techniques to bypass or manipulate MFA.

Techniques covered:

- MFA Fatigue: Repeated authentication prompts designed to trick users into approving a login.
- SIM Swapping: Taking control of a victim's phone number to intercept SMS authentication codes.
- Adversary-in-the-Middle (AiTM): Using a reverse proxy to capture authenticated session tokens.
- Impossible Travel: Detecting sign-ins from geographically distant locations within an unrealistic timeframe.

Query for repeated MFA failures:
```
index="task-4" sourcetype="azure:aad:signin" (status.errorCode=50074 OR status.errorCode=50076 OR status.errorCode=500121)
| stats count as mfa_failures values(status.errorCode) as errorCodes values(status.failureReason) as failureReasons by userPrincipalName, ipAddress
| sort - mfa_failures
```

Query for impossible travel detections:
```
index="task-4" sourcetype="azure:aad:identity_protection:riskdetection"
| where riskEventType="impossibleTravel"
| table _time, userPrincipalName, activity, ipAddress, location.countryOrRegion, riskLevel, riskEventType
| sort - _time
```

Investigation results:

- Targeted user: [igor.bicalho@finegalo.thm](mailto:igor.bicalho@finegalo.thm)
- Failed MFA error code: 500121
- Normal sign-in country code: DK
- Successful attacker authentication: 2026-03-04 13:26

## Task 5: Privilege Escalation and Persistence

After compromising an account, attackers may attempt to increase their privileges and establish persistence within the tenant.

Common techniques include:

- Assigning privileged Entra ID roles.
- Creating additional accounts.
- Registering alternative MFA methods.
- Maintaining access through compromised identities.

Basic query for role assignment activities:
```
index="task-5" sourcetype="azure:aad:audit" activityDisplayName="Add member to role"
| table _time, activityDisplayName, initiatedBy.user.userPrincipalName, targetResources{}.userPrincipalName, targetResources{}.modifiedProperties{}.newValue
| sort - _time
```

Query for newly created accounts:
```
index="task-5" sourcetype="azure:aad:audit" activityDisplayName="Add user"
| eval initiator=coalesce('initiatedBy.user.userPrincipalName','initiatedBy.app.displayName')
| eval userCreated='targetResources{}.userPrincipalName'
| table _time, activityDisplayName, initiator, userCreated
```

Query for MFA registration attempts:
```
index="task-5" sourcetype="azure:aad:audit" activityDisplayName="User started security info registration" loggedByService="Authentication Methods" operationType="Add"
| eval initiator=coalesce('initiatedBy.user.userPrincipalName','initiatedBy.app.displayName')
| table _time, activityDisplayName, initiator, initiatedBy.user.ipAddress, additionalDetails{}.value
```

Investigation results:

- Created account: [rafael.maciel@finegalo.thm](mailto:rafael.maciel@finegalo.thm)
- Assigned role: Global Administrator

## Task 6: OAuth Application Abuse

OAuth allows third-party applications to access resources without directly handling a user's password.

A malicious application can maintain access even after password changes or MFA resets if its consent grant remains active.

Two permission types are important:

- Delegated Permissions: The application acts on behalf of a signed-in user.
- Application Permissions: The application acts independently and may have tenant-wide access.

High-risk permissions include:

- Mail.Read.All
- Mail.ReadWrite.All
- Files.ReadWrite.All
- RoleManagement.ReadWrite.Directory
- Directory.ReadWrite.All
- offline_access

To investigate application consent grants:
```
index="main" sourcetype="azure:aad:audit"
activityDisplayName="Consent to application"
| eval initiator=coalesce('initiatedBy.user.userPrincipalName','initiatedBy.app.displayName')
| eval appName='targetResources{}.displayName'
| eval permissionsGranted='targetResources{}.modifiedProperties{}.newValue'
| table _time, initiator, appName, permissionsGranted
| sort - _time
```

Investigation results:

- Permission to read all mailboxes: Mail.Read.All
- Consent activity: Consent to application

## Key Takeaways

- Password spraying and brute force attacks can be identified through failed sign-in patterns.
- Conditional Access Policies enforce authentication and access requirements.
- Identity Protection detects suspicious sign-in and account behavior.
- MFA fatigue and AiTM phishing can compromise authentication processes.
- Audit Logs provide visibility into privilege escalation and persistence activities.
- OAuth consent grants can provide persistent access to organizational resources.
- Splunk helps correlate identity events and investigate suspicious activity.

## Conclusion

This room demonstrated how to identify and investigate identity-based attacks in Microsoft Entra ID using Splunk. By analyzing Sign-In and Audit Logs, security analysts can detect suspicious authentication patterns, MFA bypass attempts, privilege escalation, persistence mechanisms, and malicious OAuth applications.


