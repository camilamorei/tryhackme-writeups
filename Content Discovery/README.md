# Content Discovery

## Overview

This room focuses on discovering hidden and publicly exposed content in web applications. It covers manual discovery techniques, OSINT tools, and automated enumeration using Gobuster.

## Learning Objectives

- Discover hidden files and directories.
- Analyze robots.txt, sitemap.xml, HTTP headers, and favicons.
- Identify web frameworks and technologies.
- Use search engines and OSINT tools for content discovery.
- Explore public repositories and archived websites.
- Use Gobuster for directory, subdomain, and virtual host enumeration.

## Task 1 - Introduction

Learned the fundamentals of content discovery and its importance during web application penetration testing.

Content discovery involves identifying resources that may not be directly accessible through a website's navigation, such as administrative portals, backup files, configuration files, and hidden directories.

Three main approaches were introduced:

- Manual discovery
- Automated discovery
- Open-Source Intelligence (OSINT)

## Task 2 - Manual Discovery: Common Files

Explored common files and locations that can reveal information about a web application.

Key concepts:

- robots.txt: A file that provides crawling instructions to search engine bots and may reveal interesting directories.
- sitemap.xml: A file that lists URLs intended for search engine indexing.
- Favicon: A website icon that can help identify the underlying framework or technology.
- Well-known files: Commonly exposed resources that may reveal application information.

## Task 3 - Manual Discovery: Headers & Framework Stack

Investigated HTTP response headers and website technologies.

Key concepts:

- HTTP headers can disclose server information and additional application details.
- Custom headers may expose information that is not visible in the page content.
- Framework identification helps determine which technologies are being used.
- Outdated frameworks and exposed administration portals may introduce security risks.

## Task 4 - OSINT: Search Engines & Web Tools

Explored OSINT techniques for discovering information about web applications.

Tools and techniques:

- Google Dorking: Using advanced search operators to locate indexed resources.
- Wappalyzer: Identifying technologies and frameworks used by websites.
- Wayback Machine: Reviewing historical versions of websites.
- Search engine reconnaissance: Finding publicly indexed pages and resources.

## Task 5 - OSINT: Repositories & Archives

Investigated public repositories and archived resources for exposed information.

Key concepts:

- GitHub: Searching public repositories for accidentally exposed credentials, configuration files, and sensitive information.
- Wayback Machine: Discovering older pages and resources that may no longer be accessible through the current website.
- Amazon S3: Understanding how publicly accessible cloud storage buckets can expose files and application data.

## Task 6 - Automated Discovery: Gobuster Fundamentals

Learned how to use Gobuster to automate content discovery through wordlist-based enumeration.

Gobuster can identify directories and files by sending HTTP requests using potential resource names.

Example command:

```bash
gobuster dir -u http://TARGET -w /path/to/wordlist.txt
```

Important options:

- `dir`: Directory and file enumeration mode.
- `-u`: Target URL.
- `-w`: Wordlist used for enumeration.
- `-x`: Specify file extensions to search for.
- `-t`: Set the number of concurrent threads.

## Task 7 - Automated Discovery: Subdomains & Virtual Hosts

Explored subdomain and virtual host enumeration using Gobuster.

Subdomain enumeration example:

```bash
gobuster dns -d example.com -w /path/to/wordlist.txt
```

Virtual host enumeration example:

```bash
gobuster vhost -u http://example.com -w /path/to/wordlist.txt
```

Key concepts:

- DNS enumeration helps identify additional subdomains.
- Virtual host enumeration identifies websites hosted on the same IP address.
- HTTP response codes help distinguish valid resources from unsuccessful requests.
- The correct Host header is important when testing virtual hosts.

## Task 8 - Conclusion

Completed the room and explored different techniques for discovering hidden web application content.

Key takeaways:

- Manual content discovery through common files and HTTP headers.
- Website technology identification.
- OSINT reconnaissance using public sources.
- Repository and archive investigation.
- Automated directory and file enumeration.
- Subdomain and virtual host discovery using Gobuster.

## Skills Practiced

- Web Application Reconnaissance
- Content Discovery
- OSINT
- Google Dorking
- HTTP Header Analysis
- Technology Fingerprinting
- GitHub Reconnaissance
- Directory Enumeration
- Subdomain Enumeration
- Virtual Host Enumeration
- Gobuster
