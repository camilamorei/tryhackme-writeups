# Web Server Attacks - II

Platform: TryHackMe  
Category: Web Application Security Fundamentals  
Level: Junior Penetration Tester  
Estimated Time: 60 minutes

## Overview

This room focuses on Internet Information Services (IIS), Microsoft's web server platform for Windows.

The exercises cover IIS fingerprinting, short filename enumeration, WebDAV exploitation, ASPX web shells, common misconfigurations, and automated enumeration.

## Task 1 - Introduction

This task introduces the lab environment and its objectives.

No answer needed.

## Task 2 - IIS Fingerprinting and Enumeration

IIS can be identified by inspecting HTTP response headers.

Useful commands:

```bash
curl -I http://TARGET
curl -i http://TARGET/
```

The `Server` header may reveal the IIS version and software information.

The HTTP `OPTIONS` method can help identify supported HTTP methods.

Answers:

1. HTTP response header that reveals the IIS version:

   `Server`

2. HTTP response code after an unauthenticated PUT request to the `/webdav` directory:

   `401`

## Task 3 - IIS Tilde (Short Filename) Enumeration

Windows supports the legacy 8.3 filename format, which allows files and directories to have shorter names.

IIS tilde enumeration abuses differences in server responses to discover hidden filenames and directories.

The tilde (`~`) character is used during this enumeration technique.

A discovered backup directory contains a file named `webdav_notes.txt`, which provides credentials for the next task.

Answers:

1. Character used in IIS tilde enumeration:

   `~`

2. Legacy Windows filename format:

   `8.3`

3. Password discovered in the notes file:

   `P@ssw0rd!123`

## Task 4 - WebDAV Exploitation: Uploading an ASPX Shell

WebDAV extends HTTP with file-management capabilities.

If WebDAV is incorrectly configured, authenticated users may be able to upload files to web-accessible directories.

Credentials discovered in Task 3:

```text
Username: webdav_user
Password: P@ssw0rd!123
```

A successful HTTP PUT request that creates a file returns status code `201 Created`.

The `--ntlm` option in curl enables NTLM authentication.

Example:

```bash
curl --ntlm -u 'webdav_user:P@ssw0rd!123' \
-T cmd.aspx http://TARGET/webdav/cmd.aspx
```

Answers:

1. HTTP status code confirming successful file creation:

   `201`

2. curl flag required for NTLM authentication:

   `--ntlm`

## Task 5 - ASPX Web Shells

An ASPX web shell is a server-side ASP.NET page that accepts input and executes commands on the server.

Commands execute with the permissions of the IIS application pool identity.

Useful commands:

```bash
whoami
whoami /priv
```

The `SeImpersonatePrivilege` privilege is particularly important because it can be abused in certain Windows privilege escalation techniques, including Potato-style attacks.

Answers:

1. User account returned by `whoami`:

   `iis apppool\defaultapppool`

2. Windows privilege associated with Potato-style privilege escalation:

   `SeImpersonatePrivilege`

## Task 6 - IIS Misconfigurations

IIS misconfigurations can expose sensitive files and diagnostic information.

Common issues include:

- Directory browsing enabled
- Exposed backup files
- WebDAV misconfiguration
- Detailed error messages
- Publicly accessible diagnostic handlers
- Excessive application pool permissions

The `/uploads/` directory exposes a backup file.

ASP.NET also provides a diagnostic handler called `trace.axd`, which should not be publicly accessible in production environments.

Answers:

1. Sensitive file extension found in the `/uploads/` directory:

   `.bak`

2. ASP.NET diagnostic handler that should be disabled in production:

   `trace.axd`

## Task 7 - Automation

Automation helps identify server configurations and supported HTTP methods.

Nmap provides the `http-methods` NSE script to enumerate allowed HTTP methods.

Example:

```bash
nmap -Pn -p 80 --script http-methods TARGET
```

Answer:

1. Nmap NSE script used to enumerate HTTP methods:

   `http-methods`

## Task 8 - Conclusion

This room demonstrates how IIS fingerprinting and enumeration can reveal security weaknesses.

Key takeaways:

- HTTP headers can reveal IIS information.
- Tilde enumeration can disclose hidden filenames.
- WebDAV can introduce dangerous file upload capabilities.
- ASPX web shells execute under the IIS application pool identity.
- Exposed backup files can disclose sensitive information.
- Diagnostic handlers should not be publicly accessible.
- Nmap can automate HTTP method enumeration.

No answer needed.

## Answer Key

| Task | Answer |
|---|---|
| 2.1 | `Server` |
| 2.2 | `401` |
| 3.1 | `~` |
| 3.2 | `8.3` |
| 3.3 | `P@ssw0rd!123` |
| 4.1 | `201` |
| 4.2 | `--ntlm` |
| 5.1 | `iis apppool\defaultapppool` |
| 5.2 | `SeImpersonatePrivilege` |
| 6.1 | `.bak` |
| 6.2 | `trace.axd` |
| 7.1 | `http-methods` |

## Final Notes

IIS security testing requires understanding both Windows-specific behavior and web server configuration.

Always validate findings manually and perform testing only against systems for which you have authorization.
