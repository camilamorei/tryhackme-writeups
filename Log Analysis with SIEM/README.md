# Log Analysis with SIEM

## Overview

This room explores how Security Information and Event Management (SIEM) platforms help security analysts investigate suspicious activity by collecting, searching, and correlating logs from multiple sources.

Using Splunk, the exercises cover Windows, Linux, and web application logs to identify malicious behaviour and investigate potential security incidents.

## Learning Objectives

- Understand the benefits of SIEM for security analysts.
- Identify different log sources and their investigative value.
- Understand event correlation and log normalisation.
- Investigate Windows and Linux system activity.
- Analyse web application logs for suspicious behaviour.
- Use Splunk searches to identify indicators of compromise.

## Topics Covered

### SIEM Fundamentals

Explored centralisation, correlation, historical event analysis, and the importance of collecting logs from different systems into a unified platform.

### Log Sources Overview

Studied host-based, network-based, and web-based logs. Reviewed time zone differences and log normalisation as important considerations during investigations.

### Windows Logs

Analysed Windows Event Logs and Sysmon events to investigate suspicious process execution, network connections, account creation, service activity, and scheduled tasks.

### Linux Logs

Investigated authentication and system logs to identify failed and successful login attempts, privilege escalation, suspicious cron jobs, and possible persistence mechanisms.

### Web Application Logs

Used web access logs to investigate brute-force attacks, suspicious web shell activity, and potential distributed denial-of-service attacks.

## Key Takeaways

- SIEM platforms centralise logs and help analysts correlate events across multiple data sources.
- Log normalisation makes information from different systems easier to search and compare.
- Windows logs and Sysmon provide visibility into process execution, network connections, account changes, and persistence.
- Linux authentication and system logs help identify suspicious logins, privilege escalation, and scheduled tasks.
- Web access logs can reveal brute-force attempts, web shell activity, and abnormal request patterns.
- Splunk Search Processing Language (SPL) helps filter, correlate, and investigate security events.
- Accurate timelines require understanding the time zones and timestamps used by different log sources.

## Tools and Technologies

- Splunk
- Search Processing Language (SPL)
- Windows Event Logs
- Sysmon
- Linux auth.log
- Linux syslog
- Web server access logs
- Security Information and Event Management (SIEM)

## Conclusion

This room provided practical experience using Splunk to analyse logs from Windows, Linux, and web applications. It reinforced the importance of log centralisation, event correlation, and identifying suspicious behaviour when investigating security incidents.
