# TryHackMe SOC Fundamentals

## About the Room

This repository contains my notes and learning outcomes from the SOC Fundamentals room on TryHackMe.

The objective is to understand how a Security Operations Center works, its main components, and the responsibilities of a SOC Analyst.

## Learning Objectives

- Understand the role of a Security Operations Center.
- Learn about the People, Process, and Technology pillars.
- Understand security monitoring and incident response.
- Learn about SOC roles and responsibilities.
- Practice alert triage using the 5 Ws.
- Understand the investigation of a potential port scan.

## Topics Covered

### 1. Introduction to SOC

A Security Operations Center (SOC) is a team responsible for monitoring an organization's systems, detecting suspicious activities, and supporting incident response.

### 2. The Three Pillars

- People: security analysts, engineers, and managers.
- Process: procedures for monitoring, investigating, and responding to incidents.
- Technology: tools used to detect, analyze, and respond to threats.

### 3. SOC Roles

- Level 1 Analyst: performs initial alert triage.
- Level 2 Analyst: conducts deeper investigations.
- Level 3 Analyst: handles complex incidents and threat hunting.
- Security Engineer: configures and maintains security solutions.
- Detection Engineer: develops and improves detection rules.
- SOC Manager: coordinates the team and its operations.

### 4. SOC Processes

Common SOC processes include alert triage, investigation, escalation, incident response, and documentation.

The 5 Ws help structure an investigation:

- What happened?
- When did it happen?
- Where did it happen?
- Who was involved?
- Why did it happen?

### 5. Security Technologies

- SIEM: collects and correlates security logs.
- EDR: monitors endpoints and supports threat investigation and response.
- Firewall: filters network traffic according to security rules.
- IDS/IPS: detects suspicious network activity and can block threats.
- Antivirus: detects and helps remove malicious software.
- XDR: combines security data from multiple sources.

### 6. Practical Investigation

A potential port scan alert requires the analyst to review the available logs, identify the source and destination, establish the event timeline, and determine whether the activity is suspicious.

Investigation steps:

1. Review the alert details.
2. Identify the source and destination IP addresses.
3. Determine when the activity occurred.
4. Examine related logs and network activity.
5. Assess whether the activity is legitimate or malicious.
6. Document the findings and escalate when necessary.

## Key Takeaways

- SOC teams help protect organizations through continuous monitoring.
- Alert triage is an essential Level 1 SOC Analyst responsibility.
- Security alerts require investigation before classification.
- Accurate documentation supports incident response.
- People, Process, and Technology work together to improve security.

## Skills Practiced

- Blue Team fundamentals
- Security monitoring
- Log analysis
- Alert triage
- Incident investigation
- SIEM fundamentals
- Security incident documentation

## Reference

TryHackMe: https://tryhackme.com/

## Disclaimer

This repository contains educational notes from an authorized cybersecurity training environment.

## Status

Room: SOC Fundamentals

Platform: TryHackMe

Focus: Blue Team and SOC Analysis
