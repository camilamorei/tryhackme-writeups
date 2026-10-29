# IP and Domain Threat Intel

## Overview

This room explores how security analysts enrich IP addresses and domain indicators to investigate suspicious network activity. It focuses on DNS records, domain registration information, geolocation, Autonomous System Numbers (ASNs), exposed services, TLS certificates, and VPN detection.

## Learning Objectives

- Enrich domains using WHOIS/RDAP, DNS records, and TLS information.
- Understand ASNs and geolocation during security alert triage.
- Identify exposed services using Shodan, Censys, and VirusTotal.
- Detect VPN, proxy, and Tor exit nodes using IP intelligence services.
- Correlate information from multiple threat intelligence sources.

## Topics Covered

### Domain Enrichment

Domain investigations can reveal DNS records, registration dates, hosting infrastructure, and potential impersonation techniques.

Relevant indicators include:

- A and AAAA records
- TXT records
- Domain registration age
- Typosquatting
- Internationalized domain name (IDN) attacks
- Content Delivery Network (CDN) usage

### IP Enrichment

IP enrichment helps analysts investigate the reputation, location, and ownership of suspicious addresses.

Useful sources include VirusTotal, AbuseIPDB, IPinfo, and BGP.Tools. Analysts can use these services to identify suspicious activity and determine whether an address belongs to residential infrastructure, hosting providers, or cloud services.

### Autonomous Systems and Geolocation

An Autonomous System Number (ASN) identifies a network under a particular organization's control.

ASN information and approximate geolocation provide additional context for suspicious connections. These indicators should be correlated with other evidence rather than treated as definitive proof of malicious activity.

### Service Exposure

Shodan and Censys help analysts identify internet-exposed ports, services, software banners, and system configurations.

TLS certificate information can also provide clues about suspicious infrastructure, including certificate issuers, validity periods, and associated services.

### VPN Detection

VPN and proxy detection services help analysts determine whether an IP address may belong to anonymization infrastructure.

A familiar geolocation does not guarantee that a login is legitimate. Conversely, the absence of a VPN indicator does not automatically make an event benign.

### Threat Intelligence Challenge

The investigation process combines domain resolution, cloud provider identification, geolocation, domain registration data, and exposed service information to build a clearer picture of malicious infrastructure.

## Tools and Technologies

- VirusTotal
- AbuseIPDB
- BGP.Tools
- Shodan
- Censys
- WHOIS and RDAP
- DNS lookup tools
- IP2Proxy
- Spur
- TLS certificate lookup tools

## Key Takeaways

- DNS and domain registration information provide useful context for suspicious domains.
- IP reputation, ASN ownership, and geolocation help assess network indicators.
- Exposed services can reveal potential attack infrastructure and remote access points.
- VPN and proxy detection can add context to suspicious authentication events.
- No single intelligence source should determine a security verdict on its own.
- Correlating multiple indicators supports more accurate alert triage and incident response.

## Conclusion

This room provided practical experience with IP and domain threat intelligence, including DNS enrichment, ASN investigation, service exposure, VPN detection, and infrastructure analysis. These techniques help security analysts investigate suspicious connections and make evidence-based decisions during SOC alert triage.
