# Active Reconnaissance

## Overview

This room explores active reconnaissance techniques used to gather information by directly interacting with target systems and services.

## Topics Covered

- Web browser reconnaissance
- ICMP and ping
- Traceroute
- Telnet
- Netcat
- Service and server identification

## Tasks

### Task 1 - Introduction

Introduction to active reconnaissance and its role in information gathering.

### Task 2 - Web Browser

Explored how web browsers can be used to retrieve information from websites.

### Task 3 - Ping

Learned how to use ICMP echo requests to test connectivity.

Key findings:
- `-s`: Sets the size of the ICMP packet data.
- ICMP header size: 8 bytes.
- Windows Firewall blocks ping requests by default.

Command:

```bash
ping -c 10 MACHINE_IP
```

### Task 4 - Traceroute

Used traceroute to identify the network path between the AttackBox and the target domain.

Commands:

```bash
traceroute tryhackme.com
traceroute -T -p 443 tryhackme.com
```

Key concepts:
- Each hop represents a router along the network path.
- Traceroute can reveal the route packets take to reach a destination.
- The destination itself should not be counted as an intermediate router.

### Task 5 - Telnet

Connected to the target VM on port 80 to identify the web server.

Command:

```bash
telnet MACHINE_IP 80
```

HTTP request:

```http
GET / HTTP/1.1
Host: MACHINE_IP
```

Server identified:
- Name: Apache
- Version: 2.4.61

### Task 6 - Netcat

Connected to the target VM on port 21 to identify the FTP service.

Command:

```bash
nc MACHINE_IP 21
```

Server version:
- FTP server: 0.17

### Task 7 - Conclusion

Reviewed the active reconnaissance techniques covered throughout the room.

## Key Takeaways

- Active reconnaissance involves directly interacting with target systems.
- Ping is useful for testing network connectivity.
- Traceroute reveals intermediate network hops.
- Telnet and Netcat can be used to connect to services and inspect their banners.
- Service banners can reveal software names and versions.

## Tools Used

- Ping
- Traceroute
- Telnet
- Netcat
