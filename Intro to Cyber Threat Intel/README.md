# Intro to Cyber Threat Intel

## Overview

This room introduces Cyber Threat Intelligence (CTI) and explains how threat intelligence helps security teams understand, investigate, and respond to cyber threats. It covers intelligence classifications, the CTI lifecycle, industry frameworks, and practical threat analysis.

## Learning Objectives

- Understand the purpose of Cyber Threat Intelligence.
- Identify different threat intelligence classifications.
- Learn the six phases of the CTI lifecycle.
- Understand the Traffic Light Protocol (TLP).
- Explore MITRE ATT&CK, MITRE D3FEND, and the Cyber Kill Chain.
- Understand CVE, CVSS, NVD, STIX, and TAXII.
- Apply threat intelligence concepts during practical analysis.

## Topics Covered

### 1. Introduction to Cyber Threat Intelligence

Cyber Threat Intelligence involves collecting, processing, and analysing information about threats to produce actionable insights. It helps security teams understand adversary behaviour, identify malicious indicators, and improve defensive capabilities.

Threat intelligence can include IP addresses, domains, file hashes, malware information, and details about threat actors.

### 2. Threat Intelligence Classifications

Threat intelligence can be classified according to its purpose and the type of information it provides.

- Technical Intelligence: IP addresses, domains, file hashes, and other technical indicators.
- Strategic Intelligence: High-level information about threats, risks, and their potential business impact.
- Operational Intelligence: Information about specific campaigns, adversary activities, and attack operations.
- Tactical Intelligence: Information about adversary tactics, techniques, and procedures (TTPs).

### 3. CTI Lifecycle

The CTI lifecycle consists of six phases that transform raw data into actionable intelligence.

1. Direction: Define intelligence requirements, objectives, and investigation questions.
2. Collection: Gather information from threat feeds, open-source intelligence, internal platforms, and vendor reports.
3. Processing: Normalize, organize, correlate, and deduplicate collected data.
4. Analysis: Evaluate the relevance, reliability, and confidence of indicators.
5. Dissemination: Deliver intelligence to the appropriate teams and stakeholders.
6. Feedback: Measure results, evaluate effectiveness, and refine future intelligence requirements.

### 4. Traffic Light Protocol (TLP)

TLP defines how widely sensitive information can be shared.

- TLP:CLEAR: No restrictions on sharing.
- TLP:GREEN: Sharing permitted within the relevant community, but not publicly.
- TLP:AMBER: Sharing restricted according to the applicable need-to-know boundaries.
- TLP:RED: Sharing limited to specifically named recipients.

Analysts should preserve TLP labels when storing, processing, and distributing threat intelligence.

### 5. Threat Intelligence Formats

- STIX: A structured format for describing threat intelligence, indicators, relationships, and context in a machine-readable form.
- TAXII: A protocol for exchanging threat intelligence through APIs.

TAXII supports Collection and Channel sharing models.

### 6. CTI Standards and Frameworks

#### MITRE ATT&CK

MITRE ATT&CK documents adversary tactics and techniques. Analysts can use technique identifiers to classify observed behaviour and communicate findings consistently.

#### MITRE D3FEND

MITRE D3FEND describes defensive techniques and helps security teams identify possible countermeasures against adversary behaviour.

#### Cyber Kill Chain

The Cyber Kill Chain describes seven stages of an attack:

1. Reconnaissance
2. Weaponization
3. Delivery
4. Exploitation
5. Installation
6. Command and Control
7. Actions on Objectives

This framework helps analysts understand the progression of an attack and identify opportunities for intervention.

#### CVE, CVSS, and NVD

- CVE: Provides identifiers for publicly known vulnerabilities.
- CVSS: Provides a scoring system for assessing vulnerability severity.
- NVD: Provides vulnerability information, including CVE records, severity scores, and affected products.

### 7. Practical Threat Intelligence Analysis

The practical exercise involves building a threat profile by examining security monitoring information and identifying relevant indicators, including an email address and a downloaded file.

This demonstrates how threat intelligence can connect individual observations into a more complete picture of a potential threat.

## Key Takeaways

- CTI transforms raw threat data into actionable security intelligence.
- The CTI lifecycle provides a repeatable process for collecting, analysing, and sharing information.
- Technical indicators help analysts identify and investigate suspicious activity.
- TLP labels must be respected when sharing intelligence.
- MITRE ATT&CK and D3FEND help connect adversary behaviour with defensive measures.
- The Cyber Kill Chain provides a structured view of attack progression.
- STIX and TAXII support the representation and exchange of threat intelligence.
- Feedback helps improve the relevance and effectiveness of intelligence operations.

## Tools and Technologies

- MITRE ATT&CK
- MITRE D3FEND
- Cyber Kill Chain
- STIX
- TAXII
- MISP
- AbuseIPDB
- OpenCTI
- Splunk
- CVE
- CVSS
- National Vulnerability Database (NVD)

## Conclusion

This room demonstrates how Cyber Threat Intelligence supports security monitoring, threat investigation, and defensive decision-making. Understanding the CTI lifecycle, intelligence-sharing standards, and common security frameworks helps analysts turn collected information into meaningful actions.
