# SOC L1 Alert Triage

## Introduction

This room introduces the alert triage process used by Level 1 Security Operations Center (SOC) analysts. It explains how security alerts are generated, how to understand their properties, how to prioritize them, and how to investigate suspicious activity.

Alert triage is an essential SOC responsibility because it helps analysts identify potential threats efficiently and determine which incidents require further investigation.

## Task 1: Introduction

This task introduced the role of SOC analysts and the importance of alert triage in security operations.

## Task 2: Events and Alerts

Security alerts are generated when a security solution detects an event or sequence of events that matches a detection rule.

The process typically follows these steps:

1. An event occurs, such as a user login or process execution.
2. The system records the event in its logs.
3. Logs are forwarded to a security solution, such as a SIEM or EDR.
4. Detection rules identify suspicious activity and generate alerts.
5. SOC analysts review and investigate the alerts.

### Alert Management Solutions

* **SIEM:** Collects and analyzes logs from multiple sources and provides centralized alert management.
* **EDR:** Monitors endpoints and detects suspicious activities.
* **NDR:** Monitors network traffic to identify potential threats.
* **SOAR:** Automates and coordinates security workflows.
* **ITSM:** Helps teams manage incidents, tickets, and investigation status.

### SOC Roles

* **SOC L1 Analyst:** Performs initial alert triage and escalates potential threats.
* **SOC L2 Analyst:** Conducts deeper investigations and supports incident response.
* **SOC Engineer:** Develops and maintains detection rules and alert quality.
* **SOC Manager:** Monitors the effectiveness and quality of security operations.

## Task 3: Alert Properties

Security alerts contain information that helps analysts understand and investigate suspicious activity.

The main alert properties are:

* **Alert Time:** The time when the alert was generated.
* **Alert Name:** A summary of the detected activity.
* **Alert Severity:** Indicates the urgency of the alert.
* **Alert Status:** Shows whether the alert is new, in progress, or closed.
* **Alert Verdict:** Indicates whether the activity is malicious or benign.
* **Alert Assignee:** Identifies the analyst responsible for the investigation.
* **Alert Description:** Explains the detection logic and why the activity may be suspicious.
* **Alert Fields:** Contains relevant information about the event, such as usernames, hostnames, and command lines.

### Alert Verdicts

* **True Positive:** The alert correctly identifies genuinely suspicious or malicious activity.
* **False Positive:** The alert identifies activity that is not actually a security threat.

## Task 4: Alert Prioritization

Alert prioritization determines which alerts should be investigated first.

A basic prioritization process follows these steps:

1. Filter out alerts that have already been assigned or are being investigated.
2. Prioritize alerts according to severity.
3. When alerts have the same severity, investigate the oldest alert first.

### Severity Order

1. Critical
2. High
3. Medium
4. Low

Prioritization helps SOC analysts focus on potentially serious threats and reduce the time between detection and investigation.

## Task 5: Alert Triage

Alert triage is the process of reviewing an alert, investigating the associated activity, determining its legitimacy, and documenting the results.

### Initial Actions

* Assign the alert to the responsible analyst.
* Change the status to In Progress.
* Review the alert name, description, and relevant fields.
* Identify the affected user, host, network, or other assets.

### Investigation

During the investigation, analysts should:

* Identify the entity affected by the activity.
* Understand the action that triggered the alert.
* Review related events before and after the detection.
* Look for additional suspicious behavior.
* Use threat intelligence and available security tools to validate findings.

### Final Actions

After completing the investigation, the analyst should:

1. Determine whether the alert is a True Positive or False Positive.
2. Document the investigation and explain the reasoning behind the verdict.
3. Escalate the alert when further investigation is necessary.
4. Update the alert status to Closed when appropriate.

Correctly documenting findings helps other analysts understand the investigation and supports future incident response.

## Task 6: Conclusion

This room covered the fundamentals of SOC L1 alert triage, including alert generation, alert properties, prioritization, investigation, and final classification.

Effective alert triage enables SOC analysts to identify potential threats, distinguish malicious activity from benign events, and escalate incidents that require deeper investigation.

## Key Takeaways

* Alerts are generated when security solutions detect activity that matches defined detection rules.
* Alert severity and age help determine investigation priority.
* SOC L1 analysts perform initial investigations and escalate potential threats.
* True Positives indicate genuine malicious activity, while False Positives indicate activity that is not a real threat.
* Clear documentation and correct alert status updates are essential parts of the triage process.

## Skills Practiced

* Security alert analysis
* SOC alert prioritization
* SIEM alert management concepts
* Basic security event investigation
* True Positive and False Positive classification
* Incident documentation and escalation
