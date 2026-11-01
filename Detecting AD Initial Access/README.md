# Detecting AD Initial Access

## Overview

This room focuses on detecting initial access techniques targeting Active Directory environments. It explores how attackers exploit web applications, compromise user accounts, and gain access to internal networks through services such as Outlook Web Access (OWA) and VPN gateways.

Using Splunk, the investigation involves analyzing IIS logs, Windows Security events, Sysmon telemetry, Exchange logs, and Network Policy Server (NPS) events to identify suspicious activity and reconstruct an attack timeline.

## Objectives

- Understand how attackers gain initial access to Active Directory environments.
- Analyze IIS logs to identify suspicious HTTP requests and web shell activity.
- Detect brute-force attacks against Outlook Web Access.
- Investigate compromised Exchange accounts.
- Analyze VPN authentication events and RADIUS communication.
- Correlate endpoint, authentication, and network logs using Splunk.

## Topics Covered

### IIS Log Analysis

IIS logs provide information about HTTP requests made to web servers, including source IP addresses, requested URIs, HTTP methods, response codes, and timestamps.

These logs can help identify suspicious requests, unusual file uploads, and interactions with potentially malicious web shells.

### Web Shell Detection

A web shell allows an attacker to execute commands remotely through a compromised web server.

Common indicators include:

- Unexpected ASPX files in web directories.
- Suspicious HTTP requests to unusual pages.
- Web server processes spawning command-line interpreters.
- Unexpected file creation events.

Sysmon Event IDs 1 and 11 can help investigate process creation and file creation activity.

### Exchange and OWA Attacks

Outlook Web Access (OWA) provides web-based access to Exchange mailboxes.

Attackers may target OWA through brute-force attacks or password spraying. Windows Security Event IDs 4624 and 4625 help identify successful and failed authentication attempts.

Exchange virtual directories, including `/owa` and `/ecp`, can also provide useful evidence during an investigation.

### VPN Authentication Analysis

VPN access can provide attackers with a path into an organization's internal network.

The investigation covers Network Policy Server (NPS) events and RADIUS authentication, including:

- Event ID 6272: Network Policy Server granted access.
- Event ID 6273: Network Policy Server denied access.
- Event ID 6274: Network Policy Server discarded a request.

Correlating VPN authentication events with other logs helps identify compromised accounts and suspicious remote access.

### Log Correlation with Splunk

Splunk is used to search and correlate events from different sources.

The investigation demonstrates how to:

- Filter events by Event ID and field values.
- Identify suspicious IP addresses and usernames.
- Analyze authentication patterns.
- Investigate process and file creation activity.
- Reconstruct an attack timeline.

## Key Takeaways

- IIS logs are valuable for identifying suspicious web activity.
- Web shells can provide attackers with remote command execution.
- Windows Security logs help detect brute-force attempts and compromised accounts.
- Exchange and VPN logs provide important evidence of unauthorized access.
- NPS and RADIUS events help investigate remote authentication.
- Correlating multiple log sources provides a more complete understanding of an attack.

## Conclusion

This room demonstrates how initial access attacks against Active Directory environments can be investigated through centralized log analysis.

By combining IIS, Sysmon, Windows Security, Exchange, and NPS telemetry in Splunk, analysts can identify suspicious behavior, connect related events, and reconstruct the sequence of an intrusion.
