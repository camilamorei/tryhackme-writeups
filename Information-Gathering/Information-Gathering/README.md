# TryHackMe -  Information Gathering

## Overview

This room introduces several websites, services, and resources that can be used to gather information for cybersecurity purposes, both offensively and defensively.

The room covers tools for:

* Information gathering
* Threat intelligence
* Vulnerability research
* Malware analysis
* Technical documentation
* Proof-of-Concept (PoC) research

## Shodan

Shodan is a search engine designed to discover internet-connected devices and services.

It can provide information such as:

* IP addresses
* Open ports
* Services
* Software versions
* Countries
* Organisations
* Hostnames

Shodan also supports search filters.

Examples:

```text
country:IE
port:22
org:AS7224
hostname:example.com
```

### Practical

The practical section required searching for:

```text
apache
```

The IP address:

```text
185.243.115.47
```

was associated with the domain:

```text
tryhackme.thm
```

## VirusTotal

VirusTotal is a service used to analyse files, URLs, domains, and hashes.

It aggregates results from multiple security vendors, allowing analysts to get a general view of whether something has been detected as malicious.

### Practical

The file analysed was:

```text
invoice_payment.exe
```

The number of security vendors that identified the file as dangerous was:

```text
52
```

## CVE & CVSS

CVE (Common Vulnerabilities and Exposures) provides unique identifiers for publicly known vulnerabilities.

The general format is:

```text
CVE-YEAR-NUMBER
```

Example:

```text
CVE-2026-1337
```

The room also introduced CVSS (Common Vulnerability Scoring System), which is used to communicate the severity of vulnerabilities.

### Practical

The vulnerability researched was:

```text
CVE-2026-1337
```

Its CVSS score was:

```text
10.0
```

This corresponds to the Critical severity classification.

## Linux MAN Pages

Linux provides documentation for commands and tools through MAN pages.

They can be accessed using:

```bash
man <command>
```

For example:

```bash
man nc
```

The room used nc, also known as Netcat, as an example.

### Practical

The example command for connecting to host.example.com on port 42 was:

```bash
nc host.example.com 42
```

## GitHub

GitHub can be useful for cybersecurity research because security researchers often publish:

* Proof-of-Concept (PoC) code
* Exploit demonstrations
* Scanner scripts
* Technical research
* Vulnerability analysis

Searching for a CVE identifier can help locate repositories related to a vulnerability.

However, code found online should always be reviewed carefully before execution. A repository may contain incomplete, incorrect, or potentially malicious code.

### Practical

The vulnerability investigated was:

```text
CVE-2026-1337
```

The script in the repository used to demonstrate the vulnerability was:

```text
exploit.py
```

## What I Learned

This room demonstrated how different resources can be combined during cybersecurity research.

### Main takeaways

* Shodan → discover internet-facing devices and services.
* VirusTotal → investigate suspicious files, URLs, domains, and hashes.
* CVE → identify publicly known vulnerabilities.
* CVSS → understand vulnerability severity.
* MAN pages → access Linux tool documentation directly from the terminal.
* GitHub → research PoCs, security tools, and technical analyses.

Knowing where to search is an important part of cybersecurity. The information gathered from these resources can help during reconnaissance, vulnerability assessment, threat intelligence, and defensive investigations.
