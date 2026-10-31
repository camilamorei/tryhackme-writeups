# Splunk: Setting up a SOC Lab

## Overview

This room focuses on setting up a basic Security Operations Center (SOC) lab using Splunk Enterprise and Splunk Universal Forwarder.

The lab covers the installation and configuration of Splunk on a Linux host, forwarding system logs, creating indexes, and ingesting Apache web server logs for centralized monitoring and analysis.

## Learning Objectives

- Understand Splunk deployment architecture.
- Install Splunk Enterprise on Linux.
- Manage Splunk through the command-line interface.
- Install and configure Splunk Universal Forwarder.
- Configure data forwarding and receiving.
- Create indexes and monitor Linux log files.
- Ingest and analyze Apache access logs.
- Understand centralized forwarder management.

## Tools and Technologies

- Splunk Enterprise
- Splunk Universal Forwarder
- Linux
- Apache
- Bash
- Splunk Processing Language (SPL)

## Tasks

### Task 1: Introduction

Introduced the Coffely scenario and the purpose of building a centralized SOC monitoring environment using Splunk.

### Task 2: Splunk Deployment Architecture

Studied the main components of Splunk architecture:

- Forwarders: collect and send data from endpoints.
- Indexers: process and store incoming data.
- Search Heads: provide the interface for searching and analyzing events.
- Deployment Server: centrally manages forwarders and their configurations.

### Task 3: Linux Deployment

Installed Splunk Enterprise on Linux by extracting the installer into `/opt`.

Started Splunk and configured the administrator account.

Commands used:

```bash
tar xvzf splunk_installer.tgz -C /opt
cd /opt/splunk/bin
./splunk start --accept-license
```

Splunk Web uses port `8000` by default.

### Task 4: Managing Splunk From CLI

Explored basic Splunk administration commands.

Commands covered:

```bash
./splunk start
./splunk stop
./splunk restart
./splunk status
./splunk enable boot-start
./splunk search coffely
./splunk help search
```

Also explored the `add oneshot` command for ingesting individual log files.

### Task 5: Splunk Universal Forwarder

Installed Splunk Universal Forwarder on the Linux host.

Started the forwarder using:

```bash
./splunk start --accept-license
```

Changed its management port to `8090` to avoid conflicting with the Splunk Enterprise instance running on port `8089`.

### Task 6: Configuring the Forwarder

Configured Splunk Enterprise to receive forwarded data on port `9997`.

Created the `linux_host` index and configured the Universal Forwarder to send Linux system logs.

Commands used:

```bash
./splunk add forward-server MACHINE_IP:9997
./splunk add monitor /var/log/syslog -index linux_host
./splunk add monitor /var/log/auth.log -index linux_host
```

Generated a test event using the Linux logger utility:

```bash
logger "coffely-has-the-best-coffee-in-town"
```

Verified the event in Splunk using:

```spl
index=linux_host "coffely-has-the-best-coffee-in-town"
```

Also created a new Linux user to observe the authentication and account management events recorded in syslog.

### Task 7: Windows Forwarding

Explored how to forward Windows Security Event Logs using Splunk Universal Forwarder.

Example command:

```powershell
.\splunk.exe add monitor C:\Windows\System32\winevt\Logs\Security.evtx
```

Also learned how to enable Splunk as a deployment server:

```bash
./splunk enable deploy-server
./splunk restart
```

### Task 8: Ingesting Web Logs

Configured Splunk to continuously monitor Apache access logs.

Log source:

```text
/var/log/apache2/access.log
```

Configured the following values:

- Source type: `access_combined`
- Host: `coffelyweb`
- Index: `web`

Used SPL to search and analyze incoming web requests, including URI paths and request statistics.

Example search:

```spl
index=web
```

## Key Takeaways

- Splunk centralizes logs from different systems into searchable indexes.
- Universal Forwarders collect and transmit data to Splunk instances.
- Indexes organize incoming events for investigation.
- Linux authentication and system logs provide valuable security information.
- Apache access logs help identify web activity and suspicious requests.
- Deployment Servers simplify forwarder management in larger environments.
- SPL enables analysts to search, filter, and investigate security events.

## Conclusion

This room provided practical experience building a basic SOC lab with Splunk.

It demonstrated how to install and configure Splunk Enterprise, deploy a Universal Forwarder, collect Linux logs, and ingest Apache web server logs.

These skills provide a foundation for centralized log monitoring, security investigations, and threat detection.
