# Nmap Live Host Discovery

## Overview

This room explores how Nmap discovers live hosts on a network. It covers subnetworks, target enumeration, ARP discovery, ICMP probes, TCP and UDP probes, and reverse DNS lookups.

## Topics Covered

### 1. Subnetworks
- Understanding IP addresses and subnet masks.
- Identifying network addresses, broadcast addresses, and usable host addresses.
- Calculating the number of addresses in a subnet.

### 2. Understanding Hosts Discovery through TCP/IP Layer
- Understanding how devices communicate on a local network.
- Observing ARP requests and responses.
- Understanding how ICMP ping works.
- Identifying devices through packet exchanges.

### 3. Enumerating Targets
- Specifying individual IP addresses.
- Scanning IP ranges.
- Using CIDR notation to define network ranges.
- Understanding how Nmap determines target addresses.

### 4. Nmap Host Discovery Using ARP
- Understanding ARP-based host discovery.
- Using ARP requests to identify active devices on a local network.
- Learning why ARP discovery is useful on Ethernet networks.

### 5. Nmap Host Discovery Using ICMP
- Understanding different ICMP discovery probes.
- ICMP Echo Request.
- ICMP Timestamp Request.
- ICMP Address Mask Request.

### 6. Nmap Host Discovery Using TCP and UDP
- Understanding TCP SYN and TCP ACK probes.
- Using TCP probes to discover hosts.
- Learning how UDP probes can help identify active systems.

### 7. Reverse DNS Lookup
- Understanding reverse DNS resolution.
- Using Nmap to retrieve hostnames from IP addresses.
- Learning the difference between enabling and disabling DNS resolution.

## Useful Commands

Discover live hosts without performing a port scan:

```bash
nmap -sn 192.168.1.0/24
```

Perform ARP discovery on a local network:

```bash
sudo nmap -PR -sn 192.168.1.0/24
```

Use ICMP Echo Requests for host discovery:

```bash
sudo nmap -PE -sn 192.168.1.0/24
```

Use TCP SYN ping on port 23:

```bash
sudo nmap -PS23 -sn 192.168.1.0/24
```

Use TCP ACK ping:

```bash
sudo nmap -PA -sn 192.168.1.0/24
```

Force reverse DNS lookups:

```bash
nmap -R -sn 192.168.1.0/24
```

Disable DNS resolution:

```bash
nmap -n -sn 192.168.1.0/24
```

## Key Takeaways

- Host discovery identifies which systems are reachable before further scanning.
- ARP is commonly used to discover devices on local networks.
- ICMP, TCP, and UDP probes provide alternative discovery methods.
- CIDR notation helps define network ranges.
- Reverse DNS lookups can reveal hostnames associated with IP addresses.
- Nmap provides multiple discovery techniques that can be combined depending on the network environment.

## Tools

- Nmap
- Linux terminal
- Wireshark
- TryHackMe AttackBox

## Reference

TryHackMe - Nmap Live Host Discovery

https://tryhackme.com/room/nmap01
