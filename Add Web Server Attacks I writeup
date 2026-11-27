Web Server Attacks - I
Platform: TryHackMe
Category: Web Application Security Fundamentals
Level: Junior Penetration Tester
Estimated time: 60 minutes
Overview
This room covers reconnaissance and misconfiguration identification across four web server technologies:
- Python's built-in HTTP server
- Apache
- Node.js with Express
- Nginx
The objective is to identify the software behind each service, inspect its exposed resources, and recognize configuration mistakes that could disclose sensitive information.

The room focuses on enumeration and misconfiguration discovery rather than exploitation.
Lab setup
Start the TryHackMe target machine and connect through the AttackBox or the TryHackMe VPN.

Set the target address:
export TARGET=10.10.x.x
Replace the example address with the IP assigned to your lab.

Useful initial checks:
ping -c 1 "$TARGET"
nmap -sV -sC -p- "$TARGET"
The scan helps identify open ports and the services listening on them. Use the ports discovered in your own lab when running the commands below.
Task 1 - Introduction
The lab combines four web servers on one target machine. In a real assessment, these services could be distributed across multiple hosts.

The key idea is that every exposed web service is part of the attack surface, including temporary development servers and forgotten services.
Task 2 - Identifying Web Servers
HTTP response headers can disclose the web server software, framework, and sometimes its version.

Inspect a service with:
curl -I http://$TARGET:PORT/
curl -v http://$TARGET:PORT/
Relevant response headers include:
- Server: may identify the web server software and version.
- X-Powered-By: may disclose the application framework or runtime.
Headers are useful clues, but they can be removed or modified. Confirm findings with other evidence, such as default error pages and service behavior.
Task 3 - Python HTTP Server
Python's built-in HTTP server is useful for temporary development and file sharing. It is not intended to be exposed as a production web server.

Start by inspecting the service and its root directory:
curl -i http://$TARGET:8000/
Look for files and directories that should not be publicly accessible, including:
- .env files
- Backup archives
- Database dumps
- Configuration files
- Source code
Request a discovered file directly:
curl -i http://$TARGET:8000/.env
If a backup archive is exposed, download and inspect it:
wget http://$TARGET:8000/backup.zip
unzip -l backup.zip
unzip backup.zip -d extracted_backup
An exposed environment file or database backup may contain credentials, secrets, internal configuration, or sensitive records.
Task 4 - Apache
Apache is a widely used web server. During enumeration, check for directory listings, status pages, and forgotten backup files.
Directory listing
Request directories discovered during browsing or enumeration:
curl -i http://$TARGET/files/
If directory indexing is enabled, the server may reveal filenames and allow visitors to retrieve files directly.
Server status
Apache's mod_status module can expose server activity and request information through a status endpoint.
curl -i http://$TARGET/server-status
A publicly accessible status page can disclose operational details that should be restricted to administrators.
Backup and unlinked files
Check discovered directories for files such as:
- .bak
- .old
- .zip
- .sql
- .conf
- Internal notes or documentation
For example:
curl -i http://$TARGET/files/
Do not assume a file is safe just because the main website does not link to it. Directly accessible files are still part of the attack surface.
Task 5 - Node.js (Express)
Node.js applications commonly use Express to handle HTTP requests. Development and debugging features can disclose implementation details or sensitive configuration.

Inspect the application:
curl -i http://$TARGET:3000/
Look for:
- Debug or diagnostic endpoints
- API route listings
- Verbose error messages
- Environment variable exposure
- Publicly accessible static files
If an endpoint is discovered, request it directly and review the response:
curl -i http://$TARGET:3000/api/routes
curl -i http://$TARGET:3000/api/debug/env
Also inspect static resources linked by the application. Exposed configuration files can reveal internal paths, application settings, or secrets.

A production application should not expose debug endpoints or environment variables to unauthenticated users.
Task 6 - Nginx
Nginx is commonly deployed as a web server and reverse proxy. Check for directory indexing and exposed status information.
Autoindex
The autoindex directive controls whether Nginx generates directory listings when a directory does not contain an index file.

Request the relevant directory:
curl -i http://$TARGET:8080/files/
If indexing is enabled, inspect the listed files and determine whether any contain sensitive information.
Status endpoint
Nginx can expose connection statistics through a configured status endpoint:
curl -i http://$TARGET:8080/nginx_status
The endpoint should be restricted to trusted monitoring systems or administrative hosts.
Configuration review
When configuration files are exposed, inspect them for:
- Enabled directory indexing
- Public status locations
- Unrestricted access rules
- Internal paths and upstream services
Task 7 - Common Misconfigurations Across Servers
Several findings can occur across different web server technologies:
- Directory listing enabled
- Environment files or backups exposed
- Debug endpoints accessible without authentication
- Verbose error messages
- Status pages exposed publicly
- Sensitive static files accessible directly
- Missing or weak HTTP security headers
Security header review
Inspect response headers:
curl -I http://$TARGET:PORT/
Useful security headers include:
Header	Purpose
X-Frame-Options	Controls whether a page can be embedded in a frame
X-Content-Type-Options	Helps prevent MIME-type sniffing
Content-Security-Policy	Restricts the sources from which content can be loaded
Strict-Transport-Security	Tells browsers to use HTTPS for future connections
Referrer-Policy	Controls how much referrer information browsers send


A missing header is a finding to assess in context; it does not automatically prove that the application is vulnerable.
Nikto
Nikto can identify potentially risky web server configurations and exposed resources:
nikto -h http://$TARGET:PORT
Review the output manually. Scanner findings should be validated before being reported.
Task 8 - Conclusion
This room demonstrates why web server enumeration is an essential part of web application security testing.

The main lessons are:
1. Use response headers and server behavior to identify web technologies.
2. Inspect directories for exposed files and backups.
3. Check for publicly accessible status and debugging endpoints.
4. Review HTTP security headers.
5. Validate scanner findings manually.
6. Treat development services and forgotten files as part of the attack surface.
The goal of this stage is to understand what a server exposes and why that exposure matters before moving on to further testing.
Notes
- Replace the example target IP and ports with the values from your active lab.
- Only test systems for which you have explicit authorization.
- Record evidence for each finding, including the affected URL, response, and security impact.
