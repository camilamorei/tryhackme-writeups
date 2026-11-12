# Passive Reconnaissance

## Room Progress

100%

## Overview

This room introduces passive reconnaissance techniques used to gather information about a target through publicly available sources without directly interacting with its infrastructure.

The exercises cover domain registration, DNS records, subdomain discovery, certificate transparency, and internet-exposed services.

## Tools Covered

### WHOIS

WHOIS is used to retrieve domain registration information, including registrar details, registration dates, domain status, and name servers.

### RDAP

Registration Data Access Protocol (RDAP) is the modern successor to WHOIS. It provides structured JSON responses over HTTPS.

### nslookup

A command-line utility for querying DNS records. It supports different record types, including A, MX, TXT, and NS.

### dig

A DNS lookup utility that provides detailed query results and is useful for troubleshooting and automation.

### DNSDumpster

A passive reconnaissance tool that aggregates DNS information and helps discover subdomains, IP addresses, mail servers, and service banners.

### Certificate Transparency

Public certificate logs can reveal subdomains through certificate Subject Alternative Name (SAN) entries.

The crt.sh service allows searching these logs.

### Shodan

Shodan is a search engine for internet-connected devices and services. It indexes information such as open ports, service banners, software versions, and hosting providers.

## Practical Commands

### WHOIS

```bash
whois tryhackme.com
```

### RDAP

```bash
curl -s https://rdap.verisign.com/com/v1/domain/tryhackme.com | jq .
```

### nslookup

```bash
nslookup -type=A tryhackme.com
nslookup -type=MX tryhackme.com 1.1.1.1
nslookup -type=TXT tryhackme.com
```

### dig

```bash
dig tryhackme.com A
dig @1.1.1.1 tryhackme.com MX
dig tryhackme.com TXT
dig tryhackme.com NS
```

### Certificate Transparency

Search for subdomains using:

```text
https://crt.sh/?q=%.tryhackme.com
```

## Key Findings

- Domain registrar: Namecheap.
- Name server provider: Cloudflare.
- DNS TXT records can contain verification information and other useful data.
- DNSDumpster identified Cloudflare as the most frequent service banner.
- Shodan showed the United States as the leading country for publicly accessible Apache servers.
- Port 8080 was the third most common port for Apache.
- Port 80 was the most common port for nginx.

## Key Takeaways

- Passive reconnaissance gathers intelligence without directly probing the target.
- WHOIS and RDAP provide domain registration information.
- DNS records reveal IP addresses, mail servers, and other infrastructure details.
- DNSDumpster and Certificate Transparency logs help discover subdomains.
- Shodan provides visibility into internet-exposed services.
- Public information can reveal a significant portion of an organization's attack surface.

## Conclusion

Passive reconnaissance is an important first step in a penetration test. It allows security professionals to collect valuable information about domains, infrastructure, and exposed services while minimizing direct interaction with the target.

All reconnaissance activities should be conducted ethically and within an authorized scope.
