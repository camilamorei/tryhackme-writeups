# Nmap Post Port Scans

## Room Overview

This room explores Nmap features used after port scanning to gather additional information about discovered services and hosts.

## Topics Covered

- Service and version detection
- Operating system detection
- Traceroute
- Nmap Scripting Engine (NSE)
- Saving scan output in different formats

## Commands

### Service Detection

```bash
nmap -sV MACHINE_IP
```

Detects the services and their versions running on open ports.

```bash
nmap --version-light MACHINE_IP
```

Performs a lighter version detection scan.

### OS Detection and Traceroute

```bash
sudo nmap -O MACHINE_IP
```

Attempts to identify the target operating system.

```bash
sudo nmap --traceroute MACHINE_IP
```

Performs traceroute to discover the network path to the target.

### Nmap Scripting Engine

```bash
nmap -sC MACHINE_IP
```

Runs the default set of Nmap scripts.

```bash
nmap --script http-robots.txt MACHINE_IP
```

Checks the target's robots.txt file.

```bash
nmap --script ssh2-enum-algos -p 22 MACHINE_IP
```

Enumerates supported SSH algorithms.

### Saving Scan Output

```bash
nmap -oN scan.txt MACHINE_IP
```

Saves output in normal format.

```bash
nmap -oX scan.xml MACHINE_IP
```

Saves output in XML format.

```bash
nmap -oG scan.gnmap MACHINE_IP
```

Saves output in greppable format.

```bash
nmap -oA scan MACHINE_IP
```

Saves output in all major formats.

## Key Takeaways

- Service detection helps identify applications and their versions.
- OS detection attempts to identify the target operating system.
- NSE scripts automate information gathering and vulnerability checks.
- Nmap supports normal, XML, and greppable output formats.
- The `-oA` option saves scan results in multiple formats.

## References

- https://nmap.org/book/man.html
- https://nmap.org/nsedoc/
- https://tryhackme.com/room/nmap04
