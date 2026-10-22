# Incident Response Fundamentals

## Room Overview

This room covers the fundamentals of incident response, including incident types, severity levels, incident response frameworks, detection tools, playbooks, and a practical incident response investigation.

## Task 1: Introduction to Incident Response

Incident response is the structured process of preparing for, detecting, managing, and recovering from cybersecurity incidents while minimizing their impact.

Key learning objectives:
- Understand incidents and their severity levels.
- Identify common types of security incidents.
- Learn the SANS and NIST incident response frameworks.
- Understand incident response tools and playbooks.
- Learn the purpose of an Incident Response Plan.

## Task 2: What Are Incidents?

Security solutions collect and analyze event logs to identify potentially harmful activities. When suspicious activity is detected, the solution generates an alert.

### Alert Types

- **False Positive:** An alert indicates potentially harmful activity, but the activity is legitimate.
- **True Positive:** An alert correctly identifies harmful activity.

True positive alerts may be classified as incidents after analysis. Incidents are assigned severity levels such as low, medium, high, or critical to help prioritize response efforts.

### Answers

**Question:** What is triggered after an event or group of events points to harmful activity?

**Answer:** `Alert`

**Question:** If a security solution correctly identifies harmful activity, what type of alert is it?

**Answer:** `True Positive`

**Question:** If a fire alarm is triggered by smoke from cooking, is it a true positive or a false positive?

**Answer:** `False Positive`

## Task 3: Types of Incidents

Common types of cybersecurity incidents include:

- **Malware Infections:** Malicious software compromises or damages a system.
- **Security Breaches:** Unauthorized individuals gain access to confidential information.
- **Data Leaks:** Confidential information is exposed to unauthorized entities, intentionally or accidentally.
- **Insider Attacks:** Someone within an organization intentionally initiates an attack.
- **Denial of Service (DoS) Attacks:** A system, network, or application becomes unavailable to legitimate users due to excessive or malicious requests.

### Answers

**Question:** A user's system is compromised after downloading an email attachment. What type of incident is this?

**Answer:** `Malware Infection`

**Question:** What type of incident aims to disrupt an application's availability?

**Answer:** `Denial of Service (DoS) Attack`

## Task 4: Incident Response Process

### SANS Incident Response Framework

The SANS framework consists of six phases, remembered by the acronym PICERL.

| Phase | Description |
|---|---|
| Preparation | Establish teams, resources, procedures, and security controls before an incident. |
| Identification | Detect and identify suspicious activity or incidents. |
| Containment | Limit the impact and prevent the incident from spreading. |
| Eradication | Remove the threat from the affected environment. |
| Recovery | Restore affected systems and services to normal operation. |
| Lessons Learned | Review the incident and identify improvements for future responses. |

### NIST Incident Response Framework

The NIST framework discussed in this room groups incident response into four phases:

1. Preparation
2. Detection and Analysis
3. Containment, Eradication, and Recovery
4. Post-Incident Activity

An Incident Response Plan is a formal document that outlines the organization's procedures before, during, and after an incident. It includes roles and responsibilities, response methodology, communication plans, and escalation procedures.

### Answers

**Question:** The security team disables a machine's internet connection after an incident. Which SANS phase is being followed?

**Answer:** `Containment`

**Question:** Which NIST phase corresponds to the Lessons Learned phase of SANS?

**Answer:** `Post-Incident Activity`

## Task 5: Incident Response Techniques

### Security Solutions

| Solution | Purpose |
|---|---|
| SIEM | Centralizes logs and correlates events to identify potential incidents. |
| Antivirus (AV) | Detects known malicious programs and scans systems for malware. |
| EDR | Monitors endpoints for advanced threats and can help contain and eradicate them. |

### Playbooks and Runbooks

- **Playbooks:** Comprehensive guidelines describing how to respond to a particular type of incident.
- **Runbooks:** Detailed, step-by-step instructions for executing specific response actions.

### Answer

**Question:** What are step-by-step comprehensive guidelines for incident response called?

**Answer:** `Playbooks`

## Task 6: Lab Work Incident Response

### Scenario

A phishing email delivers a malicious attachment to multiple hosts in an organization. The investigation identifies which devices downloaded the attachment, which devices executed it, and the response actions required to contain and remediate the incident.

### Answers

**Question:** What was the name of the malicious email sender?

**Answer:** `Jeff Johnson`

**Question:** What was the threat vector?

**Answer:** `Email Attachment`

**Question:** How many devices downloaded the email attachment?

**Answer:** `3`

**Question:** How many devices executed the file?

**Answer:** `1`

**Question:** What flag was found at the end of the exercise?

**Answer:** `THM{My_First_Incident_Response}`

## Key Takeaways

- Security alerts must be analyzed to distinguish false positives from true positives.
- Incidents can involve malware, data leaks, security breaches, insider threats, or denial of service.
- The SANS and NIST frameworks provide structured approaches to incident response.
- SIEM, antivirus, and EDR solutions support detection and response.
- Playbooks provide comprehensive incident response guidance, while runbooks detail individual procedures.
- Timely containment and investigation help minimize the impact of cybersecurity incidents.

## Disclaimer

This write-up is for educational purposes and documents the concepts and answers covered in the TryHackMe Incident Response Fundamentals room.
