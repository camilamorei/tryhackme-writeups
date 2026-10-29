# Alert Triage With Splunk

## Overview

This room focuses on alert triage using Splunk in a Security Operations Center (SOC) environment. It covers the investigation of security alerts involving brute-force attacks, persistence mechanisms, and web shell activity.

## Learning Objectives

- Investigate security alerts using Splunk.
- Identify brute-force login attempts and suspicious authentication activity.
- Analyze Windows processes and scheduled tasks associated with persistence.
- Investigate web shell activity and suspicious HTTP requests.
- Extract relevant indicators from security logs.
- Correlate events to understand attacker behavior.

## Topics Covered

### Initial Access Alert

Investigated failed SSH login attempts, identified brute-force activity, and examined privilege escalation and suspicious account creation.

### Persistence Alert

Analyzed Windows event logs to identify a process responsible for creating a suspicious scheduled task. Investigated the parent process, local group enumeration, and the workstation associated with the attacker.

### Web Shell Alert

Investigated brute-force activity against a web application and analyzed HTTP requests interacting with a web shell. Examined timestamps, user-agent information, and request counts to understand the activity.

## Key Takeaways

- Authentication logs can reveal brute-force attempts and suspicious account activity.
- Process IDs and parent processes help reconstruct execution chains.
- Scheduled tasks can be abused to maintain persistence on Windows systems.
- HTTP logs provide valuable information about web shell interactions.
- Splunk helps analysts search, correlate, and investigate security events across different log sources.
- Effective alert triage requires validating evidence and connecting related events before reaching a conclusion.

## Tools and Technologies

- Splunk
- Search Processing Language (SPL)
- Linux authentication logs
- Windows event logs
- Web server logs
- Security alert investigation

## Conclusion

This room provided practical experience investigating security alerts with Splunk. It reinforced the importance of log analysis, event correlation, and identifying indicators of compromise during security investigations.

