# Slingshot

## Overview

This room focuses on investigating a compromised e-commerce web server using Elastic Stack. The scenario involves suspicious activity against Slingway Inc., where an attacker performed reconnaissance, exploited web vulnerabilities, gained administrative access, and accessed sensitive database information.

The investigation uses Apache logs to reconstruct the attack timeline and understand the techniques used throughout the compromise.

## Objectives

- Investigate suspicious web server activity.
- Identify the attacker's reconnaissance and enumeration techniques.
- Analyze directory enumeration and brute-force attempts.
- Understand how the attacker gained administrative access.
- Investigate malicious file uploads and web shell activity.
- Identify Local File Inclusion (LFI) exploitation.
- Determine which database was accessed and exported.

## Topics Covered

### Log Analysis with Elastic

The investigation uses Kibana Discover to examine Apache logs through a prepared data view.

Important investigation steps include:

- Selecting the correct data view.
- Setting an appropriate time range.
- Filtering events by source IP address.
- Examining HTTP response codes.
- Analyzing request paths and User-Agent values.

### Reconnaissance and Enumeration

Attackers often begin by gathering information about a target web server.

This room explores techniques such as:

- Network scanning with Nmap.
- Directory enumeration with Gobuster.
- Identifying exposed directories and login pages.
- Analyzing HTTP 404 responses.

### Brute-Force Attacks

The attacker attempts to obtain administrative access by repeatedly testing credentials.

The investigation focuses on identifying the brute-force tool through its User-Agent and examining the requests associated with authentication attempts.

### File Upload and Web Shell

After gaining administrative access, the attacker uploads a malicious file to the web server.

A web shell can allow remote command execution through HTTP requests, potentially giving an attacker control over the compromised system.

### Local File Inclusion

Local File Inclusion (LFI) is a vulnerability that allows an attacker to access files stored on the server through improperly handled file paths.

In this scenario, LFI is used to retrieve database credentials.

### Database Exfiltration

The final stages of the investigation involve examining activity related to phpMyAdmin and identifying the database exported by the attacker.

The attacker also modifies database contents through an import operation.

## Key Takeaways

- Apache logs provide valuable evidence during web server investigations.
- User-Agent values can help identify tools used by attackers.
- HTTP response codes reveal information about enumeration activity.
- Weak authentication can expose administrative interfaces to brute-force attacks.
- Unrestricted file uploads can lead to remote command execution.
- LFI vulnerabilities may expose sensitive configuration files and credentials.
- Database access and export activity can indicate data exfiltration.
- Building an accurate attack timeline helps determine the scope and impact of an incident.

## Conclusion

Slingshot demonstrates how multiple web application vulnerabilities and attack techniques can be combined to compromise a server.

By analyzing Apache logs in Elastic Stack, it is possible to reconstruct the attacker's actions, identify the tools used, and understand how the compromise progressed from reconnaissance to database access.
