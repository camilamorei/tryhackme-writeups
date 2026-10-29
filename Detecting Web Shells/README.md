# Detecting Web Shells

## Overview

This room focuses on detecting web shells through log analysis, file system investigation, network traffic inspection, and behavioral analysis. It explores how attackers deploy web shells to gain remote command execution and maintain access to compromised web servers.

## Learning Objectives

- Understand what web shells are and how attackers use them
- Identify suspicious activity in web server logs
- Investigate file systems for malicious scripts
- Analyze network traffic for web shell indicators
- Correlate web server logs with auditd events
- Investigate potential web shell compromises

## Web Shell Overview

A web shell is a malicious script uploaded to a web server that allows an attacker to execute commands remotely through HTTP requests.

Web shells may be used to obtain initial access, maintain persistence, perform reconnaissance, escalate privileges, move laterally, and exfiltrate data.

Attackers may deploy web shells by exploiting insecure file upload functionality, application vulnerabilities, or misconfigured permissions.

Web shells targeting different server technologies may use extensions such as `.php` and `.aspx`.

## Anatomy of a Web Shell

PHP web shells can abuse system execution functions to run operating system commands.

Examples of potentially dangerous PHP functions include:

- `shell_exec()`
- `exec()`
- `system()`
- `passthru()`

A simple web shell may receive a command through a URL parameter, execute it on the server, and return the output to the requester.

This behavior can provide attackers with remote access to the underlying operating system under the privileges of the web server process.

## Log-Based Detection

Web server access logs are a useful source of evidence when investigating web shell activity.

Important indicators include:

- Repeated requests to the same PHP file
- Unusual HTTP methods, such as PUT
- Repeated 404 responses during directory discovery
- Suspicious POST requests to upload endpoints
- Unusual or outdated User-Agent strings
- Unexpected external IP addresses
- Suspicious query strings containing parameters such as `cmd` or `exec`
- Requests without a referrer

These indicators should be analyzed together because individual events may also occur during legitimate activity.

### Auditd

`auditd` records system events and can help identify file creation, modification, and process execution.

The `ausearch` utility can search audit logs for events associated with configured rules.

Example:

```bash
ausearch -k web_shell
```

Correlating web server logs with audit events can help establish whether a suspicious HTTP request resulted in file creation or command execution.

## File System Analysis

Web shells must exist somewhere on the compromised server. Investigating web directories can reveal suspicious scripts and recently modified files.

Common web server directories include:

- `/var/www/html/`
- `/usr/share/nginx/html/`
- `/uploads/`
- `/tmp/`

Suspicious indicators include executable scripts in upload directories, unexpected filenames, double extensions, and malicious code embedded in existing application files.

### Useful Commands

Search for PHP files:

```bash
find /var/www/ -type f -name "*.php"
```

Search for PHP files modified within a specified date range:

```bash
find /var/www -type f -name "*.php" -newerct "2025-07-01" ! -newerct "2025-08-01"
```

Search recursively for potentially suspicious PHP functions:

```bash
grep -r "eval(" /var/www/html/
```

These commands can help narrow an investigation, but the results must be reviewed to distinguish malicious code from legitimate application behavior.

## Network Traffic Analysis

Network analysis allows investigators to inspect HTTP requests and responses, including payloads exchanged between clients and web servers.

Potential indicators include:

- Suspicious HTTP methods and request patterns
- Unexpected User-Agent strings
- Encoded commands in query parameters
- PHP source code submitted in upload requests
- Requests to newly created scripts
- Web server processes spawning command-line tools

### Useful Wireshark Filters

Filter HTTP PUT requests:

```wireshark
http.request.method == "PUT"
```

Find HTTP requests containing PHP in the URI:

```wireshark
http.request.uri contains ".php"
```

Inspect HTTP User-Agent fields:

```wireshark
http.user_agent
```

These filters help identify potentially suspicious traffic for further analysis.

## Investigation

The investigation exercise involved analyzing Apache access logs from a potentially compromised WordPress website.

The investigation process included:

1. Identifying suspicious client IP addresses.
2. Reviewing repeated requests and HTTP response codes.
3. Finding directories discovered during reconnaissance.
4. Identifying the PHP upload endpoint.
5. Determining which commands were executed through the web shell.
6. Investigating additional files downloaded to the server.
7. Examining the web shell source code for embedded indicators.

### Useful Investigation Commands

Review failed requests:

```bash
grep "404" /var/log/apache2/access.log
```

Filter access logs by a suspected IP address:

```bash
grep "SUSPICIOUS_IP" /var/log/apache2/access.log
```

Search for POST requests associated with PHP endpoints:

```bash
grep "POST" /var/log/apache2/access.log | grep "\.php"
```

Inspect suspicious scripts with `cat` or another text viewer to investigate their contents.

## Key Takeaways

- Web shells provide remote command execution through compromised web applications.
- Access logs can reveal reconnaissance, uploads, and repeated web shell interactions.
- File system analysis helps identify suspicious scripts and recently modified files.
- Auditd provides additional evidence of file and process activity.
- Network traffic analysis can expose malicious payloads and command execution patterns.
- Correlating multiple sources of evidence helps reconstruct an attack.
- Suspicious indicators should be investigated in context rather than treated as definitive proof on their own.

## Skills Practiced

- Apache access log analysis
- Linux command-line investigation
- File system searching with `find`
- Content searching with `grep`
- Audit log investigation with `ausearch`
- HTTP traffic analysis with Wireshark
- Web shell detection and incident investigation

## Conclusion

This room demonstrated how web shells can be detected through log analysis, file system inspection, network traffic analysis, and event correlation. These techniques are valuable for SOC analysts and incident responders investigating compromised web servers and identifying attacker activity.
