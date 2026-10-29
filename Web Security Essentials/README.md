# Web Security Essentials

## Overview

This room introduces the fundamentals of web security, explaining how web applications work, why they are common targets for attackers, and which security measures can be implemented to protect web infrastructure.

## Topics Covered

- The evolution from desktop applications to web applications
- Web application security risks
- Web infrastructure and request-response cycles
- Common web servers: Apache, Nginx, and Microsoft IIS
- Secure coding practices
- Input validation and sanitization
- Access control and authentication
- Logging and access log analysis
- Patch management and system hardening
- Content Delivery Networks (CDNs)
- Web Application Firewalls (WAFs)
- Antivirus protection
- WAF deployment types and detection techniques

## Key Concepts

### Web Infrastructure

A web service consists of three main components:

- Application: The code and resources responsible for the website's functionality and appearance.
- Web Server: Receives client requests and returns appropriate responses.
- Host Machine: The operating system and environment that run the web server and application.

### Security Measures

Application security includes secure coding, input validation, sanitization, and access control.

Web server security includes access logging, WAF deployment, and CDN integration.

Host machine security includes least privilege, system hardening, antivirus protection, and disabling unnecessary services.

Patch management helps ensure that applications, dependencies, web servers, and operating systems remain up to date.

### Content Delivery Network (CDN)

A CDN distributes cached content through servers located closer to users. It can improve performance and provide security benefits such as origin IP masking, DDoS protection, HTTPS enforcement, and WAF integration.

### Web Application Firewall (WAF)

A WAF inspects incoming HTTP traffic and can block or log potentially malicious requests.

Common deployment types include:

- Cloud-based (reverse proxy)
- Host-based
- Network-based

Common detection techniques include:

- Signature-based detection
- Heuristic-based detection
- Anomaly and behavioral analysis
- Location and IP reputation filtering

### Access Logs

Web server access logs record information about requests, including client IP addresses, timestamps, requested resources, HTTP status codes, and user agents. These records help security analysts investigate incidents and identify suspicious activity.

## Practical Exercise

The Secure-A-Site scenario involved applying security measures to three layers of a web service:

1. Web Application
2. Web Server
3. Host Machine

The exercise reinforced the importance of securing each component rather than relying on a single defensive measure.

## Key Takeaways

- Web applications are attractive targets because they are publicly accessible and often handle sensitive information.
- Security requires protecting the application, web server, and host machine.
- Logging supports monitoring, detection, and incident investigation.
- CDNs and WAFs provide additional layers of protection for web infrastructure.
- Defense in depth combines multiple security controls to reduce risk.

## Skills Practiced

- Understanding web infrastructure
- Identifying common web security controls
- Learning WAF detection methods
- Understanding access logs
- Applying basic web security hardening concepts

## Conclusion

This room provided an introduction to web security fundamentals and the defensive measures used to protect web applications and their underlying infrastructure.
