# Summit

## Overview

Summit is a practical threat detection and purple team challenge from TryHackMe. The scenario takes place at PicoSecure, where the objective is to improve malware detection and prevention capabilities by simulating adversary activity.

The challenge follows the Pyramid of Pain, progressing from lower-level indicators to more complex behaviors. Each stage requires analyzing malware artifacts and configuring defensive tools to detect or block malicious activity.

## Objectives

- Analyze suspicious executable files.
- Identify indicators of compromise (IOCs).
- Block malicious file hashes, IP addresses, and domains.
- Create Sigma rules to detect suspicious registry changes and network behavior.
- Analyze command execution patterns.
- Understand how detection and prevention increase the cost of adversary operations.

## Task 1: Challenge

### Sample 1: File Hash

The first stage focuses on identifying a malicious executable and using its hash as an indicator of compromise.

Detection method:

- Analyze the sample in the Malware Sandbox.
- Identify its hash.
- Add the hash to Manage Hashes to prevent execution.

### Sample 2: IP Address

The second stage focuses on identifying malicious network communication.

Detection method:

- Analyze the executable's network activity.
- Identify the suspicious IP address.
- Create an Egress firewall rule with the action set to Deny.

### Sample 3: Domain Name

The third stage focuses on detecting malicious domain communication.

Detection method:

- Inspect the sample's network indicators.
- Identify the malicious domain.
- Add the domain to the DNS Filter block list.

### Sample 4: Registry Activity

The fourth stage focuses on detecting changes in system behavior.

Detection method:

- Examine the sample's Windows Registry activity.
- Identify suspicious registry modifications.
- Create a Sigma rule to detect the observed behavior.

### Sample 5: Network Behavior

The fifth stage focuses on detecting recurring network activity rather than relying only on individual indicators.

Detection method:

- Analyze `outgoing_connections.log`.
- Identify the recurring pattern in the connections.
- Create a Sigma rule to detect the suspicious network behavior.

### Final Stage: Sphinx

The final stage focuses on identifying suspicious command execution patterns.

Detection method:

- Analyze `commands.log`.
- Identify the common pattern across the commands.
- Create a Sigma rule to detect the suspicious activity.

## Key Takeaways

- File hashes can identify known malicious files.
- IP addresses and domain names can be used as network indicators of compromise.
- Firewall rules can block suspicious outbound connections.
- DNS filtering can prevent access to malicious domains.
- Sigma rules provide a portable way to describe detection logic across compatible security tools.
- Behavioral detections can identify malicious activity even when individual indicators change.
- The Pyramid of Pain illustrates how detecting higher-level adversary behaviors can make attacks more difficult to sustain.

## Conclusion

The Summit challenge demonstrates how threat intelligence, malware analysis, network controls, and behavioral detection work together in a purple team exercise. Progressing through the Pyramid of Pain helps defenders move beyond isolated indicators toward detecting patterns of adversary activity.
