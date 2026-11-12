# Nmap Basic Port Scans

## Overview

This room explores Nmap port scanning techniques, focusing on TCP Connect scans, TCP SYN scans, and UDP scans. It also covers TCP flags, port states, scan scope, and performance optimization.

## Topics Covered

### 1. TCP and UDP Ports
- Understanding TCP and UDP communication.
- Common network ports and their associated services.
- Nmap's six port states:
  - Open
  - Closed
  - Filtered
  - Unfiltered
  - Open|Filtered
  - Closed|Filtered

### 2. TCP Flags
- Understanding TCP packet flags.
- SYN, ACK, RST, FIN, PSH, and URG.
- How TCP flags control connection establishment and termination.

### 3. TCP Connect Scan
- Understanding the TCP three-way handshake.
- Using Nmap TCP Connect scans.
- Identifying open and closed ports.
- Understanding how complete TCP connections are established during scanning.

Command:

```bash
nmap -sT TARGET
```

### 4. TCP SYN Scan
- Understanding half-open scanning.
- Using SYN packets to identify open ports.
- Analyzing SYN-ACK and RST responses.
- Understanding why SYN scans are commonly used.

Command:

```bash
sudo nmap -sS TARGET
```

### 5. UDP Scan
- Understanding UDP communication.
- Identifying UDP services.
- Analyzing ICMP responses.
- Understanding why UDP scans can take longer.

Command:

```bash
sudo nmap -sU TARGET
```

### 6. Fine-Tuning Scope and Performance
- Selecting specific ports.
- Scanning port ranges.
- Adjusting scan timing.
- Controlling parallel probes.
- Balancing scan speed and reliability.

Useful options:

```bash
nmap -p 80,443 TARGET
nmap -p 5000-5500 TARGET
nmap -p- TARGET
nmap -T0 TARGET
nmap --min-parallelism=64 TARGET
```

## Key Takeaways

- TCP and UDP use different communication mechanisms.
- Nmap identifies six possible port states.
- TCP Connect scans complete the TCP handshake.
- TCP SYN scans use a half-open connection technique.
- UDP scans rely on UDP responses and ICMP messages to determine port states.
- Nmap provides options to control scan scope, timing, and parallelism.
- Choosing the appropriate scan depends on the target environment and assessment requirements.

## Tools

- Nmap
- Linux terminal
- Wireshark
- TryHackMe AttackBox

## Reference

TryHackMe - Nmap Basic Port Scans

https://tryhackme.com/room/nmap02
