# Cyber Kill Chain

## Overview

This room introduces the Cyber Kill Chain, a cybersecurity model used to understand the stages of a cyberattack. It helps security professionals identify attacker behavior and determine where defensive measures can interrupt an attack.

## The Seven Stages

### 1. Reconnaissance

The attacker gathers information about the target, including domains, email addresses, employees, and exposed systems.

### 2. Weaponization

The attacker prepares a malicious payload or exploit to use against the target. This may involve malicious documents, scripts, or other tools.

### 3. Delivery

The attacker sends or introduces the malicious payload to the target. Common methods include phishing emails, malicious attachments, and compromised websites.

### 4. Exploitation

The attacker exploits a vulnerability or tricks a user into executing malicious code.

### 5. Installation

The attacker installs malware or establishes persistence to maintain access to the compromised system.

### 6. Command and Control

The compromised system communicates with infrastructure controlled by the attacker. This allows the attacker to send commands and manage the compromised device.

### 7. Actions on Objectives

The attacker attempts to achieve their goal, such as stealing data, disrupting services, or gaining access to sensitive information.

## Key Concepts

- OSINT Framework: A collection of open-source intelligence resources.
- Email harvesting: The process of collecting email addresses.
- Macros: Automated instructions that can be abused to execute malicious actions in documents.
- Watering hole attack: An attack in which a website frequently visited by the intended victims is compromised.
- Zero-day exploit: An exploit targeting a vulnerability for which an effective patch or fix is not yet available.
- Timestomping: Modifying file timestamps to conceal activity.
- Web shell: A malicious script placed on a web server to provide remote access.
- DNS tunneling: Using DNS queries and responses to communicate data or commands through DNS traffic.
- Shadow Copy: A Windows feature that creates snapshots of files or volumes.

## Practical Exercise

The following techniques can be associated with the Cyber Kill Chain stages:

| Technique | Stage |
|---|---|
| PowerShell | Weaponization |
| Spearphishing attachment | Delivery |
| Exploit public-facing application | Exploitation |
| Dynamic linker hijacking | Installation |
| Fallback channels | Command and Control |
| Data from local system | Actions on Objectives |

## Room Flag

`THM{7HR347_1N73L_12_4w35om3}`

## What I Learned

- The seven stages of the Cyber Kill Chain.
- How attackers prepare, deliver, and execute malicious payloads.
- Common techniques used to maintain access and communicate with compromised systems.
- How attacker techniques can be mapped to different stages of an attack.
- How the Cyber Kill Chain can help defenders identify opportunities to detect and interrupt malicious activity.

## Conclusion

The Cyber Kill Chain provides a structured way to understand cyberattacks from initial reconnaissance to the attacker's final objectives. Recognizing these stages helps security professionals investigate incidents, improve detection, and implement defensive measures.
