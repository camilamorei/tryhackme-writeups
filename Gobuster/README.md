# Gobuster: The Basics

## Introduction

This room introduces Gobuster, an open-source tool written in Go that is widely used in cybersecurity for reconnaissance and enumeration during penetration testing.

Gobuster uses wordlists to discover resources that may not be immediately visible on a web server or domain.

## Learning Objectives

- Understand enumeration and brute-force techniques.
- Learn how Gobuster works.
- Discover web directories and files.
- Enumerate DNS subdomains.
- Identify virtual hosts.
- Understand the differences between DNS enumeration and virtual host enumeration.

## Task 1: Introduction

This task introduces the purpose of Gobuster and its role in the reconnaissance and scanning phases of an ethical hacking assessment.

## Task 2: Environment and Setup

The practical environment uses an AttackBox and a target machine hosted by TryHackMe.

The DNS configuration must be adjusted to resolve the target domain correctly. This involves configuring the appropriate nameserver and restarting the DNSMasq service.

## Task 3: Gobuster Introduction

Gobuster supports several enumeration modes, including:

- `dir`: Enumerates web directories and files.
- `dns`: Discovers DNS subdomains.
- `vhost`: Identifies virtual hosts on a web server.
- `fuzz`: Performs fuzzing by replacing a specified keyword in requests.
- `s3` and `gcs`: Enumerate cloud storage buckets.

Gobuster uses wordlists to generate potential resource names and checks how the target responds to each request.

## Task 4: Directory and File Enumeration

Directory enumeration helps identify hidden directories and files on a web server.

This technique can reveal administrative panels, configuration files, JavaScript files, and other resources that may expose useful information during a security assessment.

HTTP status codes help determine how the server responds to each request. Gobuster does not automatically enumerate discovered directories recursively, so interesting paths may require additional scans.

## Task 5: DNS Subdomain Enumeration

DNS enumeration is used to discover subdomains associated with a target domain.

Gobuster combines entries from a wordlist with the target domain and checks which names resolve successfully.

This technique is important because subdomains may expose applications, services, or vulnerabilities that are not present on the main website.

## Task 6: Virtual Host Enumeration

Virtual host enumeration identifies different websites hosted on the same web server.

Gobuster sends HTTP requests using different hostnames and analyzes the responses to identify potentially valid virtual hosts.

DNS subdomain enumeration and virtual host enumeration are different techniques:

- DNS enumeration checks whether subdomains resolve through DNS.
- Virtual host enumeration tests hostnames through HTTP requests to a web server.

Response status codes and response lengths can help distinguish valid results from false positives.

## Task 7: Conclusion

This room provided practical experience with Gobuster and its main enumeration techniques.

The main concepts covered were directory and file discovery, DNS subdomain enumeration, virtual host discovery, wordlists, HTTP responses, and DNS resolution.

These techniques are useful during reconnaissance and authorized penetration testing because they help identify resources and services that may require further security assessment.

## Key Takeaways

- Enumeration helps discover resources exposed by a target.
- Wordlists allow Gobuster to test many possible resource names.
- Directory enumeration reveals web paths and files.
- DNS enumeration discovers subdomains through DNS resolution.
- Virtual host enumeration identifies websites hosted on the same server.
- Results should be analyzed carefully to distinguish valid findings from false positives.

## References

- TryHackMe: Gobuster: The Basics
- Gobuster official repository: https://github.com/OJ/gobuster
