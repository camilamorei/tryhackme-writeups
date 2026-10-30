# SOC L2 Alert Triage

## Overview

This room explores the alert triage workflow of a SOC Level 2 analyst, focusing on investigating escalated alerts, performing deeper log analysis, responding to threats, and learning from security incidents.

It highlights the differences between Level 1 and Level 2 responsibilities, emphasizing investigation quality, incident response, and taking initiative to improve security operations.

## Learning Objectives

- Understand the SOC Level 2 alert triage workflow.
- Identify the differences between Level 1 and Level 2 triage.
- Learn best practices for investigating escalated alerts.
- Build detailed timelines of security events.
- Understand threat containment and incident response.
- Recognize the importance of lessons learned after an incident.

## Topics Covered

### SOC L2 Workflow

The SOC Level 2 workflow typically begins when an incident is reported, most commonly through an alert escalated by a Level 1 analyst.

The workflow includes:

1. Investigating the incident.
2. Reviewing alert details and logs.
3. Responding to the threat.
4. Verifying and resolving the incident.
5. Reflecting on lessons learned.

### L1 vs L2 Alert Triage

Level 1 focuses on quickly reviewing alerts and meeting triage SLAs.

Level 2 focuses on deeper log analysis, accurate verdicts, and more advanced incident response.

Examples of L2 responsibilities include manually removing malware, disabling compromised accounts, and isolating affected hosts.

### Log Analysis

Before investigating an alert, analysts should understand the detection rule and the technique it is designed to identify.

A good investigation involves:

- Reviewing the alert and its detection rule.
- Reading the L1 analyst's investigation notes.
- Understanding what happened before and after the alert.
- Building a detailed timeline of events.
- Identifying indicators of compromise.
- Expanding the investigation when important questions remain unanswered.

### Threat Hunting Loop

The investigation process can be treated as a continuous cycle:

1. Form a hypothesis based on the alert.
2. Build a timeline to identify missing information.
3. Evaluate whether the incident is fully understood.
4. Expand or modify the investigation if necessary.

### Threat Response

Threat response begins after investigating the activity and determining its final verdict.

For confirmed threats, response actions may include:

- Quarantining malicious files.
- Disabling compromised accounts.
- Isolating affected hosts.
- Removing malware.
- Rotating compromised credentials.
- Applying security patches.

### Incident Response Phases

Three important phases of incident response are:

- Containment: Temporarily prevent the threat from spreading.
- Eradication: Remove malware, rotate stolen passwords, and revoke compromised privileges.
- Recovery: Restore normal operations, fix vulnerabilities, and monitor for reinfection.

### False Positive Response

False positives can still reveal security improvements.

Possible actions include:

- False Positive Tuning: Fixing detection rules that generate incorrect alerts.
- Security Hardening: Improving configurations and reducing security weaknesses.
- Team Improvement: Providing feedback and mentoring junior analysts.

### Lessons Learned

After resolving an incident, analysts should reflect on what worked and what could be improved.

This includes adjusting detection rules, improving procedures, sharing findings with the SOC team, and researching unfamiliar attack techniques.

## Key Takeaways

- The most common trigger for L2 triage is an escalated alert.
- Understanding the detection rule is essential before investigating an alert.
- Timelines help organize events chronologically and identify attack indicators.
- Containment prevents threats from spreading while the investigation continues.
- High-risk malicious activity may require immediate containment before confirmation.
-ery incident provides an opportunity to improve detection, response, and team procedures.

## Tools and Technologies

- SIEM
- EDR
- Splunk
- Sysmon
- Log analysis
- Threat hunting
- Incident response

## Conclusion

SOC L2 Alert Triage demonstrates that advanced alert triage involves much more than reviewing logs. Level 2 analysts must investigate incidents thoroughly, coordinate response actions, communicate findings, improve detection rules, and learn from every case.

The room emphasizes the importance of investigation quality, responsibility, and continuous improvement in Security Operations.

