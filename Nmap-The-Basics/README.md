# TryHackMe - Nmap: The Basics

Room: [Nmap: The Basics](https://tryhackme.com/r/room/nmap)  
Category: Network Security  
Topics: Host Discovery, Port Scanning, Version Detection, Timing and Output

---

## Task 1 - Introduction

This room introduces the fundamentals of Nmap, a network scanning tool used to discover live hosts, identify open ports, detect running services and collect information about target systems.

### Learning Objectives

- Discover live hosts on a network.
- Identify open TCP and UDP ports.
- Detect service versions and operating systems.
- Control scan timing.
- Save and analyze scan results.

---

## Task 2 - Host Discovery: Who Is Online?

Host discovery identifies which devices are online within a target network.

### Question 1

What is the last IP address that will be scanned when your scan target is `192.168.0.1/27`?

Answer: `192.168.0.31`

### Explanation

A `/27` subnet uses the subnet mask `255.255.255.224`, providing 32 total addresses.

- Network address: `192.168.0.0`
- Usable host addresses: `192.168.0.1` to `192.168.0.30`
- Broadcast address: `192.168.0.31`

Nmap interprets `192.168.0.1/27` as the subnet `192.168.0.0/27`, so the last address in the scanned range is `192.168.0.31`.

### Useful Commands

```bash
# Discover live hosts
nmap -sn 192.168.0.0/24

# List targets without scanning them
nmap -sL 192.168.0.1/27

# Scan a specific IP range
nmap -sn 192.168.0.1-10
```

---

## Task 3 - Port Scanning: Who Is Listening?

Port scanning identifies services listening for incoming connections on TCP and UDP ports.

### Question 1

How many TCP ports are open on the target system at `MACHINE_IP`?

Answer: `6`

### Explanation

Nmap scans the most common 1,000 TCP ports by default. The `-sS` option performs a TCP SYN scan, while `-sT` performs a TCP connect scan.

```bash
# SYN scan
nmap -sS MACHINE_IP

# TCP connect scan
nmap -sT MACHINE_IP

# Scan all TCP ports
nmap -p- MACHINE_IP

# Scan the 100 most common ports
nmap -F MACHINE_IP
```

### Question 2

Find the listening web server on `MACHINE_IP` and access it with your browser. What is the flag that appears on its main page?

Answer: `THM{SECRET_PAGE_38B9P6}`

### Explanation

The web server can be accessed through a browser using the target IP and the appropriate HTTP port. The flag is displayed on the server's main page.

```text
http://MACHINE_IP
```

If the service uses a non-default port, specify it in the URL:

```text
http://MACHINE_IP:PORT
```

### TCP and UDP Scan Options

| Option | Description |
|---|---|
| `-sT` | TCP connect scan |
| `-sS` | TCP SYN scan |
| `-sU` | UDP scan |
| `-F` | Scan the 100 most common ports |
| `-p-` | Scan all TCP ports |
| `-p1-1023` | Scan ports 1 through 1023 |
| `-Pn` | Skip host discovery and treat targets as online |

---

## Task 4 - Version Detection: Extract More Information

Nmap can identify the operating system and the software versions running on open ports.

### Question 1

What is the name and detected version of the web server running on `MACHINE_IP`?

Answer: `lighttpd 1.4.74`

### Explanation

The `-sV` option enables service and version detection.

```bash
# Detect services and their versions
nmap -sV MACHINE_IP

# Detect the operating system
sudo nmap -O MACHINE_IP

# Enable OS detection, version detection and additional features
sudo nmap -A MACHINE_IP

# Scan even if host discovery fails
nmap -Pn MACHINE_IP
```

### Important Options

| Option | Description |
|---|---|
| `-O` | Operating system detection |
| `-sV` | Service and version detection |
| `-A` | OS detection, version detection, and other features |
| `-Pn` | Treat the target as online |

---

## Task 5 - Timing: How Fast Is Fast?

Nmap provides six timing templates that control scan speed and timing behavior.

### Question 1

What is the non-numeric equivalent of `-T4`?

Answer: `-T aggressive`

### Timing Templates

| Option | Name | Description |
|---|---|---|
| `-T0` | Paranoid | Extremely slow |
| `-T1` | Sneaky | Very slow |
| `-T2` | Polite | Reduced scan speed |
| `-T3` | Normal | Default timing |
| `-T4` | Aggressive | Faster scanning |
| `-T5` | Insane | Extremely fast, potentially less reliable |

### Useful Commands

```bash
# Normal timing
nmap -T3 MACHINE_IP

# Aggressive timing
nmap -T4 MACHINE_IP

# Set a minimum packet rate
nmap --min-rate 100 MACHINE_IP

# Set a maximum packet rate
nmap --max-rate 50 MACHINE_IP

# Set a host timeout
nmap --host-timeout 30s MACHINE_IP
```

Faster scans may generate more network traffic and can miss results on unreliable networks.

---

## Task 6 - Output: Controlling What You See

Nmap supports verbose output, debugging output and several report formats.

### Question 1

What option must you add to your Nmap command to enable debugging?

Answer: `-d`

### Verbosity and Debugging

```bash
# Enable verbose output
nmap -v MACHINE_IP

# Increase verbosity
nmap -vv MACHINE_IP

# Enable debugging output
nmap -d MACHINE_IP

# Increase debugging detail
nmap -d2 MACHINE_IP
```

### Saving Scan Results

| Option | Description |
|---|---|
| `-oN filename` | Normal output |
| `-oX filename` | XML output |
| `-oG filename` | Grepable output |
| `-oA basename` | Save all major output formats |

Example:

```bash
nmap -sV MACHINE_IP -oA nmap-results
```

This creates files with `.nmap`, `.xml`, and `.gnmap` extensions.

---

## Task 7 - Conclusion and Summary

### Question 1

What kind of scan will Nmap use if you run `nmap MACHINE_IP` with local user privileges?

Answer: `Connect Scan (-sT)`

### Explanation

Without sufficient privileges to send raw packets, Nmap generally uses a TCP connect scan (`-sT`). When run with sufficient privileges, Nmap normally uses a TCP SYN scan (`-sS`) by default.

### Nmap Quick Reference

| Command | Purpose |
|---|---|
| `nmap -sn TARGET` | Discover live hosts |
| `nmap -sL TARGET` | List targets |
| `nmap -sT TARGET` | TCP connect scan |
| `nmap -sS TARGET` | TCP SYN scan |
| `nmap -sU TARGET` | UDP scan |
| `nmap -sV TARGET` | Detect service versions |
| `nmap -O TARGET` | Detect operating system |
| `nmap -A TARGET` | Enable advanced detection |
| `nmap -p- TARGET` | Scan all TCP ports |
| `nmap -F TARGET` | Scan the 100 most common ports |
| `nmap -T4 TARGET` | Use aggressive timing |
| `nmap -v TARGET` | Enable verbose output |
| `nmap -d TARGET` | Enable debugging |
| `nmap -oA FILE TARGET` | Save reports in all major formats |

---

## What I Learned

- How to discover live hosts using Nmap.
- How to perform TCP SYN, TCP connect and UDP scans.
- How to identify open ports and running services.
- How to detect service versions and operating systems.
- How to control scan speed and timing.
- How to enable verbose and debugging output.
- How to export scan results for later analysis.

Disclaimer: All scanning activities should be performed only against systems you own or have explicit authorization to test.
