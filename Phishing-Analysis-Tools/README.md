# Phishing Analysis Tools

## Overview

This room explores tools and techniques used to investigate suspicious emails, identify indicators of compromise, and determine whether messages or attachments are malicious.

The exercises cover email header analysis, URL and IP reputation checks, attachment hashing, malware sandboxes, and phishing investigation workflows.

## Task 1: Introduction

This task introduces the objectives of phishing analysis and explains how the skills from previous rooms can be applied to real-world phishing investigations.

## Task 2: Identifying Artifacts

Email analysis begins by collecting relevant artifacts from the message header and body.

Header artifacts include:
- Sender email address
- Sender IP address
- Email subject
- Recipient addresses, including To, CC, and BCC
- Reply-To address
- Date and time

Body artifacts include:
- URLs and hyperlinks
- Attachment names and extensions
- Attachment hashes

Collecting these artifacts helps establish the legitimacy of an email and supports further investigation.

## Task 3: Email Header Analysis

Email header analysis helps identify the message's origin, routing path, sender authentication results, and possible inconsistencies.

Tools covered:

- Google Messageheader: analyzes email headers and displays routing information.
- Message Header Analyzer: provides details about message transmission and header fields.
- IPinfo: provides IP address information, including geographic location and associated organization.
- URLScan.io: investigates websites and records their behavior in a controlled browsing environment.
- Cisco Talos Reputation Center: checks the reputation of IP addresses, domains, and other indicators.

These tools help analysts identify suspicious infrastructure and investigate email authentication results such as SPF.

## Task 4: Email Body Analysis

Email body analysis focuses on identifying malicious links, suspicious attachments, and hidden indicators.

URLs can be extracted by copying link addresses, examining raw email content, or using tools such as CyberChef and URL extraction services.

Attachments should be downloaded and examined only in a controlled environment.

To calculate the SHA256 hash of a file in Linux, use:

```bash
sha256sum filename.pdf
```

The resulting hash can be searched in threat intelligence services to determine whether the file has previously been identified as malicious.

Tools covered:

- CyberChef
- URL Extractor
- Cisco Talos Reputation Center
- VirusTotal

## Task 5: Malware Sandboxes

Malware sandboxes allow analysts to observe suspicious files and URLs in isolated environments without exposing their primary systems to potential threats.

Tools covered:

- ANY.RUN: interactive malware analysis with process and network monitoring.
- Hybrid Analysis: provides automated analysis reports and indicators of compromise.
- Joe Sandbox: performs static and dynamic analysis of suspicious files and URLs.

Sandbox reports can reveal process execution, network connections, downloaded payloads, and changes made to the system.

## Task 6: Using PhishTool

PhishTool centralizes phishing email investigation by presenting message artifacts, authentication results, transmission details, URLs, and attachment information.

Its VirusTotal integration provides additional reputation and detection information.

The platform also supports documenting investigation findings, identifying indicators of compromise, classifying suspicious messages, and resolving cases.

A structured investigation helps ensure that findings can be reviewed and used to improve detection rules.

## Task 7: Your Account Is on Hold

This investigation focuses on identifying phishing indicators in an email impersonating a reputable brand.

The analysis involves:
- Identifying the impersonated brand
- Determining the intended recipient
- Extracting the sender IP from the Received header
- Investigating the Return-Path domain
- Examining a shortened URL associated with the account update button

The exercise demonstrates how header fields and embedded links can expose inconsistencies that are not immediately visible in the rendered email.

## Task 8: Update Payment Details

This task uses ANY.RUN to investigate a suspicious PDF attachment associated with a fake payment update notification.

The analysis involves:
- Identifying the sandbox classification
- Recording the malicious PDF filename
- Collecting the file's MD5 hash
- Identifying the URL accessed by the PDF
- Determining the IP address associated with the destination domain

These artifacts can be used to correlate file behavior with network activity and threat intelligence results.

## Task 9: Excel Executable

This task investigates a suspicious Excel attachment through an ANY.RUN sandbox report.

The investigation focuses on:
- Identifying the malicious Excel filename
- Finding suspicious processes created after execution
- Examining the full path of a malicious binary
- Identifying the CVE associated with the attempted exploitation
- Determining the domain used to download additional malware
- Identifying the network threat associated with the download

Process trees, file paths, network connections, and vulnerability references help explain how a malicious document can initiate further compromise.

## Task 10: Conclusion

This room demonstrates a structured workflow for investigating phishing emails and their associated artifacts.

The main lessons include:

- Collect email headers and body artifacts before drawing conclusions.
- Verify sender addresses, authentication results, and routing information.
- Investigate URLs and IP addresses using reputation services.
- Calculate file hashes and search for known detections.
- Use isolated malware sandboxes to observe suspicious behavior.
- Document indicators of compromise and investigation findings.

These techniques support phishing triage, threat intelligence research, and incident response in a security operations environment.
