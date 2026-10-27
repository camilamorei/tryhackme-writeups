# Unified Kill Chain

## Overview

This room introduces the Unified Kill Chain (UKC), a cybersecurity framework developed by Paul Pols and published in 2017. It helps security professionals understand the different phases of a cyberattack, from initial reconnaissance to achieving the attacker's objectives.

The framework contains 18 phases and complements other cybersecurity frameworks, including MITRE ATT&CK and the Cyber Kill Chain.

## What Is a Kill Chain?

A Kill Chain is a model that describes the stages an attacker follows to compromise a target. Understanding these stages helps defenders identify suspicious activities, investigate incidents, and implement security controls to prevent or interrupt attacks.

The term originated in the military.

## Threat Modelling

Threat modelling is the process of identifying potential threats, vulnerabilities, and risks affecting systems and applications.

An asset is any valuable resource within an IT environment, including hardware, software, and data.

## Unified Kill Chain Phases

### Goal: In (Initial Foothold)

These phases focus on gaining initial access to a target environment.

- Reconnaissance: Gathering information about the target.
- Weaponization: Preparing the infrastructure and resources needed for an attack.
- Social Engineering: Manipulating people into performing actions that benefit the attacker.
- Exploitation: Taking advantage of vulnerabilities to execute code or gain access.
- Persistence: Maintaining access to a compromised system.
- Defence Evasion: Avoiding security controls and detection.
- Command and Control: Establishing communication between the attacker and compromised systems.
- Pivoting: Using a compromised system to reach other systems or network segments.

### Goal: Through (Network Propagation)

These phases focus on expanding access within the target environment.

- Discovery: Identifying users, systems, services, permissions, and network resources.
- Privilege Escalation: Obtaining higher levels of access.
- Execution: Running malicious code or commands.
- Credential Access: Stealing usernames, passwords, hashes, or other authentication material.
- Lateral Movement: Moving between systems within a network.

### Goal: Out (Action on Objectives)

These phases focus on collecting information and achieving the attacker's final goals.

- Collection: Gathering valuable information from compromised systems.
- Exfiltration: Transferring data out of the target environment.
- Impact: Disrupting operations or affecting the confidentiality, integrity, or availability of data.
- Objectives: Achieving the attacker's strategic goal.

The Unified Kill Chain contains 18 phases in total. The categories above summarize the phases covered in this room.

## Important Concepts

- Phishing: Using deceptive messages to trick users into opening malicious attachments, following malicious links, or revealing credentials.
- Social Engineering: Manipulating people to obtain access or information.
- Weaponization: Preparing attack infrastructure and resources.
- Exploitation: Abusing a vulnerability in a system or application.
- Persistence: Maintaining access after compromising a system.
- Defence Evasion: Avoiding detection by security tools.
- Pivoting: Using one compromised system to access other systems.
- Privilege Escalation: Gaining additional permissions.
- Credential Access: Obtaining authentication information. Mimikatz can be used to extract credentials and secrets.
- Exfiltration: Moving stolen data out of a target environment.
- Confidentiality: Ensuring that information is accessible only to authorized parties.

## Practical Exercise

The practical task involves matching attacker activities to the corresponding Unified Kill Chain phases.

The key is to identify the objective of each activity. For example, collecting information corresponds to reconnaissance, maintaining access corresponds to persistence, stealing credentials corresponds to credential access, and transferring stolen data outside the network corresponds to exfiltration.

## What I Learned

- The purpose of the Unified Kill Chain framework.
- The importance of threat modelling and identifying IT assets.
- How to distinguish between attack phases such as exploitation, persistence, and privilege escalation.
- How attackers use credential access, pivoting, and lateral movement to expand their control.
- How collection, exfiltration, and impact can affect an organization's data and operations.
- How the Unified Kill Chain complements other cybersecurity frameworks.

## Conclusion

The Unified Kill Chain provides a structured approach to understanding cyberattacks. By mapping attacker behavior to individual phases, security professionals can better investigate incidents, identify weaknesses, and improve defensive measures.
