
# OWASP Top 10 2025: IAAA Failures

## Overview

This room explores three categories from the OWASP Top 10 2025 related to failures in Identity, Authentication, Authorisation, and Accountability (IAAA).

The categories covered are:

- A01: Broken Access Control
- A07: Authentication Failures
- A09: Logging and Alerting Failures

## Task 1: Introduction

The room introduces common security weaknesses in web applications and demonstrates how failures in identity management, authentication, authorisation, and accountability can expose sensitive information or allow unauthorised actions.

## Task 2: What is IAAA?

IAAA stands for Identity, Authentication, Authorisation, and Accountability.

- Identity: The unique account representing a user or service.
- Authentication: Verifying that an identity is genuine.
- Authorisation: Determining which resources and actions an identity is allowed to access.
- Accountability: Recording and monitoring actions so they can be attributed to an identity.

### Answer

`Identity, Authentication, Authorisation, Accountability`

## Task 3: A01 Broken Access Control

Broken Access Control occurs when an application fails to enforce permissions for requested resources and actions.

One common example is an Insecure Direct Object Reference (IDOR), where changing an identifier in a URL allows access to another user's information.

Privilege escalation can be divided into two types:

- Horizontal privilege escalation: Accessing another user's data or resources without changing to a higher privilege level.
- Vertical privilege escalation: Gaining access to functionality or permissions associated with a higher privilege level.

### Answers

1. `Horizontal`
2. `THM{Found.the.Millionare!}`

## Task 4: A07 Authentication Failures

Authentication Failures occur when an application does not correctly verify a user's identity or securely manage authentication sessions.

Common examples include:

- Username enumeration.
- Weak passwords and missing rate limits.
- Authentication logic flaws.
- Insecure session management.
- Account confusion caused by inconsistent username handling.

In this challenge, registering a username with different capitalization allows access to the administrator's account because the application handles usernames insecurely.

### Answer

Flag: `THM{Account.confusion.FTW!}`

## Task 5: A09 Logging and Alerting Failures

Logging and Alerting Failures occur when security-relevant events are not properly recorded, monitored, or reported.

Effective security logging should record authentication successes and failures, account changes, administrative actions, and suspicious activity. Logs should be centrally stored, protected against tampering, and retained long enough to support investigations.

### Answers

1. Attacker IP: `203.0.113.45`
2. Compromised username: `admin`
3. Endpoint accessed: `/supersecretadminstuff`

## Task 6: Conclusion

This room demonstrates how failures in IAAA implementation can compromise web application security.

Key lessons:

- Broken Access Control: Enforce authorisation checks on every server-side request.
- Authentication Failures: Use secure authentication flows, rate limiting, unique canonical usernames, and proper session management.
- Logging and Alerting Failures: Record security events, protect logs, and alert defenders to suspicious activity.

A secure application must verify identities, authenticate users, enforce permissions, and maintain reliable records of security-relevant actions.

## Key Terms

- IAAA: Identity, Authentication, Authorisation, Accountability.
- IDOR: Insecure Direct Object Reference.
- Horizontal Privilege Escalation: Accessing resources belonging to another user at the same privilege level.
- Vertical Privilege Escalation: Gaining access to higher-level privileges.
- Authentication: Verification of an identity.
- Authorisation: Enforcement of permissions.
- Security Logging: Recording events for monitoring and investigation.
- Alerting: Notifying defenders about suspicious or potentially malicious activity.

## Status

Completed
