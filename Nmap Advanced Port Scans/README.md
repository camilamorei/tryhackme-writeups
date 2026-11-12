# Nmap Advanced Port Scans

## Overview

This room explores advanced Nmap scanning techniques, including TCP flag-based scans, firewall evasion, IP spoofing, decoy scans, packet fragmentation, and idle scans.

## Topics Covered

### 1. TCP Null, FIN, and Xmas Scans

- Understanding TCP flag manipulation.
- Null scan: sends TCP packets without setting any flags.
- FIN scan: sends packets with only the FIN flag set.
- Xmas scan: sets FIN, PSH, and URG flags.
- Analyzing responses to identify open, closed, and filtered ports.

Useful commands:

```bash
nmap -sN TARGET
nmap -sF TARGET
nmap -sX TARGET
```

### 2. TCP Maimon Scan

- Understanding the Maimon scan.
- Sending TCP packets with FIN and ACK flags.
- Analyzing target responses.

Command:

```bash
nmap -sM TARGET
```

### 3. TCP ACK, Window, and Custom Scans

- Understanding TCP ACK scans.
- Mapping firewall rules.
- Using TCP Window scans to analyze response window sizes.
- Creating custom TCP flag combinations.

Useful commands:

```bash
nmap -sA TARGET
nmap -sW TARGET
nmap --scanflags RST TARGET
```

### 4. Spoofing and Decoys

- Understanding source IP spoofing.
- Changing the source MAC address.
- Using decoy addresses to obscure the origin of a scan.
- Understanding the limitations of spoofed packets.

Useful commands:

```bash
nmap -S 10.10.10.11 TARGET
nmap -D 10.10.20.21,10.10.20.28,ME TARGET
nmap --spoof-mac 0 TARGET
```

### 5. Fragmented Packets

- Understanding IP packet fragmentation.
- Splitting packets into smaller fragments.
- Learning how fragmentation can affect firewall and IDS inspection.

Useful commands:

```bash
nmap -f TARGET
nmap -ff TARGET
```

### 6. Idle/Zombie Scan

- Understanding idle scanning.
- Using a third-party host as a zombie.
- Learning how Nmap can infer port states without directly revealing the attacker's IP address to the target.

Command:

```bash
sudo nmap -sI ZOMBIE_IP TARGET
```

### 7. Getting More Details

- Understanding Nmap output verbosity.
- Using scan reason information.
- Enabling debugging output.

Useful commands:

```bash
nmap --reason TARGET
nmap -v TARGET
nmap -vv TARGET
nmap -d TARGET
```

## Key Takeaways

- TCP flags can be manipulated to perform different types of port scans.
- Null, FIN, and Xmas scans use unusual TCP flag combinations.
- ACK scans are useful for analyzing firewall filtering behavior.
- Window scans examine TCP window values in responses.
- IP spoofing and decoys can obscure the apparent source of scanning traffic.
- Packet fragmentation changes how IP packets are transmitted.
- Idle scans use a third-party host to perform indirect port discovery.
- Nmap provides verbosity and debugging options for more detailed scan analysis.

## Tools

- Nmap
- Linux terminal
- Wireshark
- TryHackMe AttackBox

## Reference

TryHackMe - Nmap Advanced Port Scans

https://tryhackme.com/room/nmap03
