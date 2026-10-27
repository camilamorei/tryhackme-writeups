# Eviction

## Overview

Eviction is a TryHackMe room focused on threat intelligence and adversary behavior analysis using the MITRE ATT&CK framework.

The scenario follows Sunny, a Security Operations Center (SOC) analyst at E-corp. After receiving intelligence about a potential attack by APT28, Sunny must investigate the group's tactics, techniques, and procedures (TTPs) to determine whether the organization has been compromised and identify ways to stop the attack.

The room uses the MITRE ATT&CK Navigator to explore the techniques associated with the adversary.

## Objectives

- Analyze APT28 behavior using MITRE ATT&CK.
- Identify reconnaissance and initial access techniques.
- Investigate execution and persistence mechanisms.
- Recognize system discovery and lateral movement activity.
- Identify potential targets for intellectual property theft.
- Understand proxy techniques that may be used for command and control or data exfiltration.

## Task 1: Understand the Adversary

### 1. Reconnaissance and Initial Access

Technique: Spearphishing Link

Spearphishing links use targeted messages to persuade victims to visit malicious websites or interact with attacker-controlled resources. This can support reconnaissance or initial access, depending on the context.

### 2. Resource Development

Answer: Email Accounts

Adversaries may obtain or compromise email accounts during resource development to prepare infrastructure and support future operations.

### 3. User Execution

Answers:

- Malicious File
- Malicious Link

User execution techniques rely on victims interacting with malicious content. This may include opening a harmful file or clicking a malicious link.

### 4. Scripting Interpreters

Answers:

- PowerShell
- Windows Command Shell

Scripting interpreters allow adversaries to execute commands and scripts on compromised systems. Analysts should monitor their use for suspicious command execution and obfuscated scripts.

### 5. Registry-Based Persistence

Answer: Registry Run Keys

Adversaries may modify registry run keys to maintain persistence across system restarts or user logons. Analysts should investigate unexpected changes to these keys.

### 6. System Binary Proxy Execution

Answer: Rundll32

Rundll32 is a legitimate Windows utility that can be abused to execute code through dynamic-link libraries. Suspicious use may indicate defense evasion or proxy execution.

### 7. Network Discovery

Answer: Network Sniffing

Network sniffing involves monitoring network traffic to collect information about communications and activity. The presence of tools such as tcpdump on an unexpected host may warrant investigation.

### 8. Lateral Movement

Answer: SMB/Windows Admin Shares

Adversaries may abuse SMB and Windows administrative shares to access remote systems and move laterally through a network.

### 9. Collection Target

Answer: SharePoint

SharePoint may contain internal documents, business information, and intellectual property. Analysts should investigate unusual access or collection activity involving these repositories.

### 10. Proxy Techniques

Answers:

- External Proxy
- Multi-hop Proxy

Adversaries may use proxies to obscure the origin of their traffic and make command-and-control communications or data exfiltration more difficult to trace.

## Key Takeaways

- MITRE ATT&CK provides a structured way to understand adversary behavior.
- Spearphishing and user execution can help attackers gain access to systems.
- PowerShell and Windows Command Shell should be monitored for suspicious activity.
- Registry modifications may indicate attempts to establish persistence.
- Legitimate system utilities can be abused to evade security controls.
- Network sniffing and remote service abuse can support discovery and lateral movement.
- Monitoring access to collaboration platforms and information repositories can help protect intellectual property.
- Proxy infrastructure can make malicious communications more difficult to attribute.

## Conclusion

The Eviction room demonstrates how threat intelligence and MITRE ATT&CK can help SOC analysts investigate a suspected adversary. By mapping techniques to observable activity, defenders can identify suspicious behavior, investigate potential compromise, and improve detection and response capabilities.
