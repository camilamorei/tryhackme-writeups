# Network Traffic Basics

## Overview

This room introduces Network Traffic Analysis (NTA), explaining its purpose, the information that can be observed in network packets, common network traffic sources and flows, and methods used to capture and analyze network traffic.

## Task 2: What is the Purpose of Network Traffic Analysis?

Network Traffic Analysis helps security analysts monitor network performance, identify anomalies, investigate suspicious communications, and validate security alerts.

It can also help reconstruct attacks and detect activities such as DNS tunneling, command and control communications, and data exfiltration.

Answer:
- DNS tunneling

## Task 3: What Network Traffic Can We Observe?

Network packets contain information from different layers of the TCP/IP model.

The application layer contains protocol headers and application data. The transport layer includes TCP or UDP information, such as ports, flags, and sequence numbers. The internet layer contains IP addresses and fragmentation information. The link layer includes MAC addresses.

Answers:
- ZIP attachment size: 10485760 bytes
- IDS evasion technique: fragmentation
- TCP header field used to detect session hijacking: sequence number

## Task 4: Network Traffic Sources and Flows

Network traffic sources are divided into endpoint and intermediary devices.

Endpoint devices include computers, servers, mobile devices, printers, and IoT devices. Intermediary devices include routers, switches, firewalls, proxies, and IDS/IPS systems.

Network flows are commonly divided into:
- North-South: Traffic entering or leaving the local network.
- East-West: Traffic moving within the local network.

Answers:
- Device category generating the most traffic: Endpoint
- Service contacted for SMB authentication: Kerberos
- TLS: Transport Layer Security

## Task 5: How Can We Observe Network Traffic?

Network traffic can be analyzed using three main sources:

- Logs: Record selected events and connection details.
- Full Packet Capture: Collects packet-level information for detailed inspection.
- Network Statistics: Provides metadata about network flows.

Common packet capture methods include network taps and port mirroring. Port mirroring duplicates traffic from one switch port to another monitoring port. Cisco refers to this feature as SPAN.

Common analysis tools include Wireshark, tcpdump, Snort, Suricata, and Zeek.

Network flow metadata can be collected using NetFlow and IPFIX.

The room also includes interactive exercises involving HTTP and DNS traffic. The flags must be obtained from the corresponding traffic captures in the static site.

## Task 6: Conclusion

This room covers the fundamentals of Network Traffic Analysis, including packet structure, traffic sources, network flows, packet capture methods, and traffic analysis tools.

These concepts provide a foundation for investigating suspicious network activity and using Wireshark in subsequent rooms.

## Key Takeaways

- Network Traffic Analysis provides visibility into network communications.
- Logs alone may not contain enough information to investigate an incident.
- Packet captures allow analysts to inspect protocol headers and application payloads.
- Sequence numbers can help identify suspicious TCP session activity.
- DNS tunneling can be used to hide command and control communications.
- NetFlow and IPFIX provide metadata about network traffic.
