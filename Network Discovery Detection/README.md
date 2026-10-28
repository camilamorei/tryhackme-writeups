# Network Discovery Detection

## Overview

This room explores network discovery techniques and how security analysts can detect scanning activity. It covers the differences between external and internal scanning, horizontal and vertical port scanning, and common methods used to identify live hosts and open ports.

The exercises use network logs and Kibana to investigate suspicious activity and distinguish potential attacker behavior from legitimate network discovery.

## Task 1: Introduction

Network discovery is an early stage of an attack in which an attacker gathers information about a target network, its hosts, exposed services, and possible vulnerabilities.

Security analysts monitor discovery activity to identify reconnaissance and detect signs that an attacker may already have access to the internal network.

## Task 2: Network Discovery

Attackers perform network discovery to identify accessible assets, IP addresses, ports, operating systems, running services, and service versions that may contain exploitable vulnerabilities.

Defenders also use network discovery to maintain an asset inventory, identify unnecessary exposed services, and reduce the organization's attack surface.

SOC analysts must distinguish authorized scanning from suspicious activity using allowlists, threat intelligence, and behavioral detection rules.

Answer:

- Information scanned besides IP addresses, ports, and OS versions: `Services`

## Task 3: External vs Internal Scanning

External scanning occurs when a source outside the organization probes its publicly accessible systems. This activity is commonly associated with the reconnaissance phase of the MITRE ATT&CK framework.

Internal scanning occurs when a host inside the network probes other internal systems. It may indicate that an attacker has already gained access and is preparing for lateral movement.

Internal scanning generally requires more urgent investigation because the source may be a compromised device.

Answers:

- Log file containing internal scanning activity: `log-session-2.csv`
- Number of log entries for the internal scanning activity: `2276`
- External IP address performing external scanning: `203.0.113.25`

## Task 4: Horizontal vs Vertical Scanning

Horizontal scanning occurs when a source probes the same destination port across multiple IP addresses. It can help an attacker identify systems exposing a specific service.

Vertical scanning occurs when a source probes multiple ports on a single destination IP address. It can help identify the services running on a particular host.

A mixed scan combines both approaches.

Answers:

- IP range scanned horizontally: `203.0.113.0/24`
- IP address scanned vertically: `192.168.230.145`
- Ports scanned on the host exposing common services: `80, 445, 3389`

## Task 5: The Mechanics of Scanning

### Ping Sweeps

A ping sweep sends ICMP requests to multiple addresses to identify responsive hosts. Repeated ICMP activity from one source across an entire subnet can indicate a ping sweep.

### TCP SYN Scans

TCP SYN scanning uses the TCP handshake to infer whether a port is open, closed, or filtered without necessarily completing a full connection.

The Zeek connection state `S0` indicates that a connection attempt was observed without a response from the responder. This can be consistent with a SYN scan, depending on the surrounding traffic and context.

### UDP Scans

UDP scanning sends packets to UDP ports and observes responses. A closed UDP port may return an ICMP destination-unreachable message, while an open or filtered port may not respond immediately.

Analysts should correlate several indicators before classifying traffic as a scan.

Answers:

- Source IP performing a ping sweep: `192.168.230.127`
- Scan type performed by `203.0.113.25` against `192.168.230.145`: `TCP SYN Scan`
- UDP scanning attempts detected: `N`

## Investigation Workflow

The room uses CSV network logs exported from a SIEM. Useful Linux commands for inspecting these logs include:

```bash
head -n 2 log-session-1.csv
```

To inspect filenames in the logs directory:

```bash
ls -lh ~/Downloads/logs/
```

When investigating scanning activity, compare source addresses, destination addresses, destination ports, timestamps, and connection states.

Kibana can also be used to search the available logs, add relevant fields as columns, and filter events to identify repeated connection patterns.

## Key Takeaways

- Network discovery helps attackers identify hosts, services, and potential vulnerabilities.
- External scanning is commonly associated with reconnaissance.
- Internal scanning can indicate a compromised host and possible lateral movement.
- Horizontal scanning targets the same port across multiple IP addresses.
- Vertical scanning targets multiple ports on a single IP address.
- Ping sweeps use ICMP to discover responsive hosts.
- TCP SYN scans use TCP connection behavior to probe ports.
- UDP scans can be difficult to identify because some ports do not return a response.
- Log correlation and traffic context help distinguish authorized discovery from suspicious activity.

