# Alert Triage With Elastic

## Overview

This room focuses on investigating security alerts using Kibana, part of the Elastic Stack. The exercises involve analysing IIS web server logs, Windows Security events, and Sysmon data to investigate suspicious activity targeting a fictional company called SomeCorp.

The investigation follows an attack sequence involving web exploitation, suspicious administrator access, account creation, privilege changes, PowerShell execution, and archive creation.

## Learning Objectives

- Use Kibana to search and analyse security logs.
- Identify indicators of compromise in web server logs.
- Investigate suspicious HTTP requests and potential web shell activity.
- Analyse Windows authentication events and process execution.
- Correlate events across multiple log sources.
- Investigate account creation and security group modifications.
- Reconstruct an attack timeline using log evidence.

## Topics Covered

### Kibana and Elastic Stack

Configured the Kibana data view and time range to access relevant logs. Used queries and selected fields to filter events and organise investigation results.

### Web Attack Investigation

Analysed IIS logs to investigate suspicious POST requests associated with ProxyLogon exploitation. Examined GET requests to an ASPX file and identified command execution patterns consistent with web shell activity.

### Windows Authentication and Account Activity

Investigated Windows Security Event ID 4624 to verify administrator logons. Used event timestamps, record IDs, and source IP addresses to correlate authentication activity with earlier web requests.

### Process Execution and Persistence

Analysed Sysmon process creation events to understand process relationships and command execution. Investigated the creation of a new user account and modifications to local security groups.

### PowerShell Investigation

Examined PowerShell script block logs to identify commands executed during the attack. Used timestamps and command details to connect attacker activity across different stages of the investigation.

### Archive Creation

Investigated the execution of Rar.exe to determine which account used the utility and identify the resulting archive. This demonstrated the importance of investigating potentially legitimate tools in the context of suspicious activity.

## Key Takeaways

- Web server logs can reveal exploitation attempts and suspicious requests.
- Windows Security logs provide evidence of authentication and account management activity.
- Sysmon helps analysts investigate process execution and parent-child relationships.
- Correlating timestamps, IP addresses, usernames, and process details helps reconstruct attack sequences.
- Account creation and security group modifications can indicate persistence and privilege escalation.
- PowerShell logs provide visibility into commands executed by an attacker.
- Legitimate utilities can be abused during an attack, making contextual analysis essential.
- Clear evidence and a reconstructed timeline support effective incident escalation.

## Tools and Technologies

- Elastic Stack
- Kibana
- IIS web server logs
- Windows Security Event Logs
- Sysmon
- PowerShell logs
- Elastic query syntax
- Indicators of Compromise (IoCs)

## Conclusion

This room provided practical experience conducting alert triage with Elastic and Kibana. It reinforced the importance of correlating web and host-based logs, investigating suspicious account activity, analysing command execution, and building an evidence-based attack timeline for escalation.
