# Wireshark: Packet Operations

## Overview

This room covers packet analysis using Wireshark, focusing on traffic statistics, protocol details, packet filtering, advanced filtering operators, and configuration profiles.

## Task 2: Statistics | Summary

Wireshark provides statistical tools that help analysts understand a packet capture and identify endpoints, conversations, protocols, and network services.

Useful sections include:

- Resolved Addresses: Displays IP addresses and hostnames identified in the capture.
- Protocol Hierarchy: Shows protocols and their packet counts.
- Conversations: Displays communication between pairs of endpoints.
- Endpoints: Lists unique network endpoints.
- Name Resolution: Can display readable hostnames, service names, and manufacturer information.

Answers:

- IP address of the hostname starting with `bbc`: `199.232.24.81`
- Number of IPv4 conversations: `435`
- Data transferred from the Micro-St MAC address: `7474` kB
- IP addresses linked with Kansas City: `4`
- IP address associated with Blicnet: `188.246.82.7`

## Task 3: Statistics | Protocol Details

Wireshark provides protocol-specific statistics for IPv4, IPv6, DNS, and HTTP. These statistics help identify frequently contacted hosts, DNS response times, and HTTP activity.

Answers:

- Most used IPv4 destination address: `10.100.1.33`
- Maximum DNS service request-response time: `0.467897`
- HTTP requests by `rad[.]msn[.]com`: `39`

## Task 4: Packet Filtering | Principles

Wireshark supports two main types of packet filters.

Capture filters

Capture filters are configured before packet capture begins. They determine which packets are collected and saved. For example:

```text
tcp port 80
```

Display filters

Display filters are used to show only packets matching specific conditions in an existing capture. They can be changed at any time during analysis.

Examples:

```text
ip.src == 10.10.10.100
tcp.port == 80
dns
http
```

Common comparison operators include `==`, `!=`, `>`, `<`, `>=`, and `<=`. Logical operators include `and`, `or`, and `not`.

## Task 5: Packet Filtering | Protocol Filters

Protocol filters allow analysts to narrow packet captures by network addresses, transport ports, and application protocols.

Common examples:

```text
ip
ip.ttl < 10
tcp.port == 4444
http.request.method == "GET"
dns.flags.response == 0
dns.qry.type == 1
```

Answers:

- Number of IP packets: `81420`
- Packets with a TTL value less than 10: `66`
- Packets using TCP port 4444: `632`
- HTTP GET requests sent to port 80: `527`
- Type A DNS queries: `51`

## Task 6: Advanced Filtering

Wireshark provides advanced operators and functions to search packet fields and match patterns.

The `contains` operator searches for a case-sensitive string within a field.

```text
http.server contains "IIS"
```

The `matches` operator searches a field using a regular expression.

```text
http.host matches "\\.(php|html)"
```

The `in` operator checks whether a value belongs to a specified set.

```text
tcp.port in {3333 4444 9999}
```

Functions such as `upper()`, `lower()`, and `string()` can transform values before filtering.

Answers:

- Microsoft IIS packets not originating from port 80: `21`
- Microsoft IIS packets with version 7.5: `71`
- Packets using ports 3333, 4444, or 9999: `2235`
- Packets with even TTL values: `77289`
- Bad TCP Checksum packets in the Checksum Control profile: `34185`
- Packets displayed by the existing filtering button: `261`

Example filters used for these investigations:

```text
http.server contains "IIS" && !(tcp.srcport == 80)
http.server matches "IIS.*7.5.*"
tcp.port in {3333 4444 9999}
string(ip.ttl) matches ".*[02468]$"
tcp.checksum_bad.expert
```

The final filtering-button exercise requires selecting the existing button in the Checksum Control profile and checking the resulting packet count.

## Task 7: Conclusion

This room introduced Wireshark statistics, protocol analysis, display filters, advanced operators, and configuration profiles. These features help analysts narrow down large packet captures, identify suspicious communication, and investigate network activity at the packet level.

## Key Takeaways

- Statistics provide an overview of network conversations, endpoints, and protocols.
- Display filters make it easier to isolate packets relevant to an investigation.
- TCP and UDP filters can narrow traffic by port.
- DNS and HTTP filters help investigate application-level communication.
- Advanced operators and functions support more complex packet searches.
- Wireshark profiles allow analysts to maintain different configurations for different investigation tasks.
