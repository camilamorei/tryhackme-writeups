# Modern Web Stacks

## Overview

This room explores four common web application stacks and demonstrates how to identify and exploit vulnerabilities in each one.

The focus is on fingerprinting web technologies, identifying vulnerable versions, researching CVEs, and understanding how specific vulnerabilities can be exploited.

## Learning Objectives

- Identify web stacks through HTTP headers, cookies, error messages, and HTML patterns.
- Fingerprint MERN, Next.js, Django, and LAMP applications.
- Identify vulnerable software versions.
- Understand and exploit real-world CVEs.
- Perform authentication bypass, SQL injection, path traversal, and remote code execution.

## Task 1: Introduction

The room introduces a three-step workflow for web application testing:

1. Fingerprint the technology stack using observable HTTP signals.
2. Confirm the software version and identify applicable CVEs.
3. Execute the exploit chain and understand the vulnerability's root cause.

The lab provides four services:

- Port 3000: MERN / Express
- Port 3001: Next.js
- Port 8000: Django
- Port 8080: Apache 2.4.49

## Task 2: MERN Stack

This task focuses on identifying a MERN application and analyzing its exposed technologies.

Fingerprinting indicators include:

- `X-Powered-By: Express`
- `connect.sid` session cookie

The MERN stack consists of MongoDB, Express.js, React, and Node.js.

Topics:
- HTTP header analysis
- Session cookie identification
- Express.js fingerprinting
- Node.js application reconnaissance

## Task 3: React / Next.js

This task explores Next.js fingerprinting and an authentication bypass vulnerability.

CVE-2025-29927 affects Next.js middleware authorization and can allow attackers to bypass middleware-based authentication under vulnerable configurations.

Fingerprinting indicator:

- `window.__next_f`

Topics:
- Next.js identification
- Middleware authentication
- CVE-2025-29927
- Authentication bypass
- HTTP request header manipulation

## Task 4: Django

This task focuses on identifying a Django application and exploiting a SQL injection vulnerability.

CVE-2021-35042 affects Django versions using vulnerable URL validation behavior in the `Truncator` functionality.

Fingerprinting indicators include:

- `csrfmiddlewaretoken`
- Django-specific application behavior

Topics:
- Django fingerprinting
- CSRF tokens
- CVE-2021-35042
- SQL injection
- Database extraction

## Task 5: LAMP

This task explores Apache 2.4.49 and its path traversal vulnerability.

CVE-2021-41773 affects Apache HTTP Server 2.4.49 and allows path traversal. Under specific conditions, including CGI configuration, it can also lead to remote code execution.

Important techniques:

- Identifying Apache versions through HTTP headers
- Path traversal
- Arbitrary file disclosure
- CGI execution
- Using `--path-as-is` to preserve crafted URL paths during requests

Topics:
- Linux
- Apache
- MySQL
- PHP
- CVE-2021-41773
- Path traversal
- Remote code execution

## Task 6: Automation

This task introduces automated web server vulnerability scanning with Nikto.

Example command:

```bash
nikto -h http://MACHINE_IP:PORT
```

Nikto helps identify potentially dangerous files, outdated server software, insecure configurations, and known vulnerabilities.

Automated scanning can speed up reconnaissance, but findings should always be manually validated.

## Task 7: Conclusion

The room demonstrates how understanding a web application's technology stack can significantly improve penetration testing efficiency.

Identifying the framework and version helps narrow down the attack surface and makes targeted vulnerability research possible.

## Skills Practiced

- Web application fingerprinting
- HTTP header analysis
- Cookie identification
- Next.js middleware analysis
- Authentication bypass
- SQL injection
- Django reconnaissance
- Apache vulnerability assessment
- Path traversal
- Remote code execution
- Automated vulnerability scanning with Nikto
- CVE research
