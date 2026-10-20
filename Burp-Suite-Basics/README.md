# Burp Suite: The Basics

## Room Information

- Platform: TryHackMe
- Room: Burp Suite: The Basics
- Category: Web Application Security
- Difficulty: Beginner
- Status: Completed
- Link: https://tryhackme.com/room/burpsuitebasics

## Objectives

The objective of this room was to understand the fundamentals of Burp Suite, a platform widely used for web application penetration testing and security assessments.

The room covered the Burp Suite interface, configuration options, proxy functionality, browser integration, target scoping, HTTPS interception, and a practical example of a Cross-Site Scripting (XSS) vulnerability.

## Tasks and Topics Covered

### Task 1: Introduction

Introduction to the Burp Suite: The Basics room and its learning objectives.

### Task 2: What is Burp Suite?

Learned about Burp Suite as a platform for intercepting, inspecting, and modifying HTTP and HTTPS traffic between a browser and a web server.

Reviewed the available editions:

- Burp Suite Community Edition
- Burp Suite Professional
- Burp Suite Enterprise

Answers:
- Edition that performs continuous web application scanning: Burp Suite Enterprise
- Application types commonly tested with Burp Suite: Web and mobile applications

### Task 3: Burp Community Features

Explored the main tools available in Burp Suite Community Edition:

- Proxy: Intercepts and modifies HTTP requests and responses.
- Repeater: Allows requests to be modified and resent.
- Intruder: Automates customized requests for fuzzing and testing.
- Decoder: Encodes and decodes data.
- Comparer: Compares data at the word or byte level.
- Sequencer: Analyzes the randomness of tokens and session identifiers.

Answers:
- Tool used to intercept requests: Proxy
- Tool used for login form brute-force testing: Intruder

### Task 4: Installation

Reviewed the installation process for different operating systems, including Kali Linux, Windows, and macOS.

Burp Suite Community Edition is available for free and is commonly included in Kali Linux installations.

### Task 5: The Dashboard

Learned about the main sections of the Burp Suite dashboard:

- Tasks
- Event Log
- Issue Activity
- Advisory

Answer:
- Section that displays Burp Suite actions and connection details: Event Log

### Task 6: Navigation

Explored the main tabs, subtabs, and keyboard shortcuts used to navigate Burp Suite.

Answer:
- Keyboard shortcut Ctrl + Shift + P: Proxy tab

### Task 7: Options

Reviewed global user settings and project-specific settings, including configuration categories, update behavior, hotkeys, and TLS client certificates.

### Task 8: Introduction to the Burp Proxy

Learned how the Proxy intercepts, records, and allows modification of HTTP requests and responses. Also explored HTTP history, WebSockets history, response interception, and Match and Replace rules.

### Task 9: Connecting Through the Proxy

Learned how to configure the FoxyProxy Basic browser extension to route Firefox traffic through Burp Suite.

Proxy configuration:
- Proxy IP: 127.0.0.1
- Proxy port: 8080

### Task 10: Site Map and Issue Definitions

Explored the Target tab and learned how to map web application pages, review vulnerability definitions, and identify unusual endpoints.

The practical challenge involved navigating the target application and examining its site map to locate an unusual endpoint.

### Task 11: The Burp Suite Browser

Learned how to use the built-in Chromium browser, which is preconfigured to route traffic through Burp Proxy.

Also reviewed the browser sandbox configuration and its security implications when running Burp Suite as root.

### Task 12: Scoping and Targeting

Learned how to define the target scope to focus testing on specific domains or IP addresses.

Key steps:
- Add the target to scope.
- Configure Burp to stop logging out-of-scope traffic.
- Set interception rules to only intercept requests within the target scope.

### Task 13: Proxying HTTPS

Learned how to configure a browser to trust the PortSwigger Certificate Authority (CA) certificate, allowing HTTPS traffic to be inspected through Burp Proxy.

The process involved downloading the certificate from http://burp/cert and importing it into the browser's certificate authorities.

### Task 14: Example Attack

Performed a practical demonstration of reflected Cross-Site Scripting (XSS) using a support form in the authorized TryHackMe lab.

The exercise demonstrated how client-side validation can be bypassed by intercepting and modifying an HTTP request.

Example payload:

```html
<script>alert("Succ3ssful XSS")</script>
```

The payload was URL-encoded before forwarding the intercepted request.

### Task 15: Conclusion

Completed the room and reviewed the fundamentals of Burp Suite, including proxy configuration, request interception, browser integration, scoping, HTTPS inspection, and basic web vulnerability testing.

## Key Security Takeaways

- Burp Proxy is essential for inspecting and manipulating HTTP and HTTPS traffic during authorized security assessments.
- Proper target scoping reduces unnecessary traffic and helps keep testing focused.
- Repeater and Intruder support different types of manual and automated testing.
- HTTPS interception requires the browser to trust the Burp Certificate Authority.
- Client-side validation must not be treated as a security boundary.
- Web applications should validate input on the server side and implement appropriate output encoding to prevent XSS vulnerabilities.
- Security testing must only be performed against systems for which authorization has been granted.

## What I Learned

This room provided a practical introduction to Burp Suite and its role in web application penetration testing. I learned how to configure a proxy, intercept and modify requests, navigate the site map, define a target scope, and inspect HTTPS traffic.

I also gained a better understanding of reflected XSS and why client-side input validation alone is insufficient to protect web applications.

These fundamentals will help me continue studying web application security and practice more advanced techniques using Burp Suite Repeater and other tools.

## Completion

Room: Burp Suite: The Basics

Platform: TryHackMe

Status: Completed
