# Detecting Web Attacks

## Overview

This room covers common web attacks and the techniques used to detect them through log analysis, network traffic inspection, and Web Application Firewalls (WAFs).

## Topics Covered

- Client-side attacks
- Cross-Site Scripting (XSS)
- Server-side attacks
- SQL Injection (SQLi)
- Log-based attack detection
- Network-based attack detection
- Web Application Firewalls (WAFs)
- Custom WAF rules

## Client-Side Attacks

Client-side attacks target users and their devices rather than directly exploiting the web server. These attacks may take advantage of browser behavior, user interactions, or vulnerabilities in client-side code.

Cross-Site Scripting (XSS) is a common example. It allows an attacker to inject malicious scripts into web pages that are viewed by other users.

## Server-Side Attacks

Server-side attacks target web applications, servers, or their underlying infrastructure.

SQL Injection (SQLi) occurs when an application handles untrusted input unsafely in database queries. An attacker may exploit this vulnerability to retrieve, modify, or delete database information.

## Log-Based Detection

Web server and application logs can provide evidence of suspicious activity.

Useful indicators include:

- Unusual User-Agent values
- Repeated login attempts
- Requests to sensitive endpoints
- Suspicious query parameters
- SQL injection payloads
- Requests associated with directory fuzzing

Analysts can investigate these indicators to identify potential attacks and determine which resources were targeted.

## Network-Based Detection

Network traffic can reveal malicious activity that may not be obvious from application logs alone.

Inspecting HTTP requests, responses, and suspicious payloads can help identify exploitation attempts, credential attacks, and unauthorized data access.

## Web Application Firewalls

A Web Application Firewall (WAF) inspects and filters web requests to help protect applications from malicious traffic.

WAF rules can identify suspicious patterns in incoming requests and block traffic that matches defined conditions.

For example, a custom rule can block requests containing a specific User-Agent value associated with unwanted automated activity.

WAFs are an additional layer of defense and should be combined with secure coding practices, monitoring, and regular updates.

## Key Takeaways

- Client-side and server-side attacks target different parts of a web application environment.
- XSS and SQL injection are important web vulnerabilities to understand.
- Logs help analysts identify suspicious requests and attack patterns.
- Network traffic analysis provides additional evidence during investigations.
- WAFs can inspect requests and block traffic that matches security rules.
- Effective detection combines multiple sources of evidence rather than relying on a single indicator.

## Skills Practiced

- Identifying common web attacks
- Analyzing web application logs
- Recognizing suspicious HTTP requests
- Understanding SQL injection indicators
- Inspecting network traffic
- Understanding WAF rules and filtering

## Conclusion

This room demonstrates how web attacks can be detected through log analysis, network inspection, and request filtering. These techniques are useful for security analysts investigating suspicious activity and protecting web applications.
