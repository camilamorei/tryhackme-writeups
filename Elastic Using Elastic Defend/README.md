# Elastic: Using Elastic Defend

## Overview

This room explores Elastic Defend and its role in endpoint security. It focuses on how security analysts can monitor endpoint activity, investigate suspicious behavior, and detect potential threats using Elastic Security.

## Objectives

- Understand the purpose of Elastic Defend.
- Configure and explore the Elastic Defend integration.
- Monitor endpoint telemetry and security events.
- Investigate suspicious processes and file activity.
- Analyze security alerts and their risk scores.
- Explore process relationships using the Analyzer.
- Understand how detection rules identify malicious behavior.

## Topics Covered

### Elastic Defend

Elastic Defend is an endpoint security solution that collects telemetry and helps detect suspicious activity across monitored systems. It provides visibility into processes, files, network connections, and other endpoint events.

### Endpoint Telemetry

Endpoint telemetry provides information about activities occurring on a monitored machine. Important event fields include:

- `process.name`
- `process.executable`
- `process.parent.executable`
- `event.dataset`
- `network.type`
- `source.ip`

These fields help analysts understand what happened and identify potentially suspicious behavior.

### Alert Investigation

Elastic Security generates alerts when activity matches configured detection rules. Analysts can investigate alerts by examining:

- Alert severity and risk score.
- Related processes and files.
- Network connections.
- MITRE ATT&CK tactics and techniques.
- Event timelines and supporting telemetry.

### Process Analysis

The Analyzer helps visualize relationships between processes. By examining parent and child processes, analysts can understand how an activity started and identify suspicious execution chains.

### Persistence and Suspicious Activity

The room also explores techniques that attackers may use to maintain access to a compromised system, including scheduled tasks and cron jobs.

Understanding these behaviors helps analysts recognize persistence mechanisms and investigate potential compromises.

## Key Takeaways

- Endpoint detection provides visibility into system activity.
- Process relationships are essential for investigating suspicious execution.
- Risk scores help prioritize security alerts.
- Detection rules can identify behaviors associated with known attack techniques.
- MITRE ATT&CK helps classify adversary tactics and techniques.
- Investigating multiple event sources provides better context during incident response.

## Conclusion

This room demonstrates how Elastic Defend can support endpoint monitoring and threat detection. It provides practical experience with endpoint telemetry, alert investigation, process analysis, and identifying suspicious behavior.

These skills are useful for understanding endpoint security and improving defensive security investigations.
