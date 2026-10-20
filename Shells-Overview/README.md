# TryHackMe Shells Overview

## About the Room

This repository contains my notes and key takeaways from completing the Shells Overview room on [TryHackMe](https://tryhackme.com/).

The goal of this room is to understand the main types of shells used in offensive security, penetration testing, and vulnerability analysis.

## Learning Objectives

- Understand how Reverse Shells work.
- Understand how Bind Shells work.
- Learn about Web Shells and their applications.
- Learn about listeners and connection tools.
- Understand how command injection vulnerabilities can be exploited.
- Understand the risks of unrestricted file uploads.
- Learn methods for detecting and preventing these vulnerabilities.

## Concepts Studied

### 1. Reverse Shell

A Reverse Shell is a connection in which a compromised machine initiates an outbound connection to a machine controlled by the operator, allowing remote shell access.

Tool studied: Netcat (`nc`).

### 2. Bind Shell

A Bind Shell opens a port on the target machine and waits for incoming connections. Once a connection is established, it can provide access to the system shell.

### 3. Web Shell

A Web Shell is a script accessed through a web application that may allow commands to be executed on the server when an exploitable vulnerability exists.

### 4. Tools and Technologies

- Netcat: network connections and listeners.
- Socat: communication between sockets.
- Ncat: a network connection tool from the Nmap project with additional features.
- rlwrap: improves command-line interaction.
- Python: process execution and socket creation.
- PHP: a programming language commonly used in web applications.

## Practical Exercises

During this room, I explored laboratory scenarios involving:

- Command injection in web applications.
- Establishing Reverse Shells and Bind Shells.
- Unrestricted file uploads.
- Using Web Shells in test environments.
- Locating files and flags on a laboratory machine.

All practical exercises should be performed exclusively in authorized environments.

## Security and Prevention

- Validate and sanitize user input.
- Avoid executing system commands with untrusted data.
- Restrict the types and sizes of uploaded files.
- Store uploaded files outside publicly accessible directories.
- Run applications with the principle of least privilege.
- Monitor network connections and suspicious processes.
- Use firewall rules and security monitoring tools.

## Key Takeaways

Completing this room helped me strengthen my understanding of Reverse Shells, Bind Shells, and Web Shells, while demonstrating how vulnerabilities in web applications can compromise server security.

I also learned about tools commonly used in penetration testing and the importance of identifying, safely testing, and remediating security vulnerabilities.

## Conclusion

Room completed: TryHackMe Shells Overview

Study areas: Cybersecurity | Penetration Testing | Web Security

Platform: [TryHackMe](https://tryhackme.com/)

This repository was created for educational purposes, to document my learning journey and develop my cybersecurity skills.
