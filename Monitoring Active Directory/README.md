# Monitoring Active Directory

## Overview

This room focuses on monitoring Active Directory environments using Windows Event Logs and Splunk. It explores how authentication, account management, and directory activities generate security events that can be used to identify suspicious behavior.

The exercises demonstrate how defenders can investigate authentication requests, monitor user and group changes, and understand how domain controllers record activity across a Windows domain.

## Objectives

- Understand how Active Directory authentication works.
- Identify important Windows Security Event IDs.
- Monitor Kerberos authentication activity.
- Investigate successful and failed logon attempts.
- Track user account creation and group membership changes.
- Use Splunk to search and analyze Windows Event Logs.
- Recognize suspicious activity through event correlation.

## Topics Covered

### Active Directory Fundamentals

- Domain controllers and domain authentication.
- Local accounts versus domain accounts.
- Kerberos authentication.
- LDAP, SMB, RDP, and NTLM.
- The role of the NTDS database in storing Active Directory information.
- Computer accounts and their naming conventions.

### Windows Security Event Logs

The room explores several important Event IDs used in Active Directory monitoring:

- 4624: Successful logon.
- 4625: Failed logon.
- 4768: Kerberos Ticket Granting Ticket (TGT) request.
- 4769: Kerberos service ticket request.
- 4771: Kerberos pre-authentication failure.
- 4776: NTLM authentication.
- 4720: User account created.
- 4728: Member added to a global security group.
- 4732: Member added to a local security group.
- 4756: Member added to a universal security group.
- 5136: Directory object modified.

### Authentication Monitoring

Authentication events provide useful information about how users and systems access domain resources.

By analyzing Kerberos and Windows logon events, defenders can identify:

- Unusual authentication patterns.
- Repeated authentication failures.
- Unexpected service ticket requests.
- Suspicious account activity.
- Potential credential abuse.

### Logon Types

Windows records different logon types to describe how an account authenticated.

Some important examples include:

- Type 2: Interactive logon.
- Type 3: Network logon.
- Type 5: Service logon.
- Type 7: Unlock.
- Type 10: Remote Interactive logon.

Understanding these values helps distinguish normal user activity from potentially suspicious access.

### Splunk Investigation

Splunk was used to search and analyze Windows Security Event Logs.

The exercises introduced SPL commands such as:

- `search` to filter events.
- `stats` to calculate statistics.
- `top` to identify the most frequent values.
- `sort` to organize results.
- `dc()` to count distinct values.

These commands help transform large amounts of Windows event data into useful security information.

## Key Takeaways

- Active Directory generates valuable security telemetry that can be used to monitor domain activity.
- Kerberos events are important for investigating authentication behavior.
- Windows Event IDs provide context about logons, account creation, and group membership changes.
- Monitoring group modifications can help identify unauthorized privilege escalation.
- Computer accounts can be distinguished from regular user accounts through their naming conventions.
- Splunk makes it easier to search, filter, correlate, and investigate Windows Security Event Logs.
- Establishing a baseline of normal activity helps defenders recognize unusual behavior.

## Conclusion

This room provided practical experience with monitoring Active Directory through Windows Security Event Logs and Splunk.

Understanding authentication protocols, recognizing important Event IDs, and investigating account activity are essential skills for detecting suspicious behavior in Windows domain environments.
