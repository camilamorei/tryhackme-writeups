# Snort

## Overview

This room introduces Snort, an open-source network intrusion detection and prevention system. It covers Snort modes, configuration files, packet logging, IDS and IPS concepts, PCAP analysis, and the structure of Snort rules.

## Learning Objectives

- Understand the differences between HIDS, HIPS, NIDS, and NIPS.
- Identify Snort configuration files and loaded rules.
- Use Snort to sniff and log network traffic.
- Analyze packets and PCAP files.
- Understand Snort rule headers, options, and rule revisions.

## Task 2: Introduction

The `.easy.sh` script outputs:

```text
Too Easy!
```

## Task 3: IDS and IPS Concepts

| Question | Answer |
|---|---|
| Solution that stops threats on a local machine | HIPS |
| Solution that detects threats on a local network | NIDS |
| Solution that detects threats on a local machine | HIDS |
| Solution that stops threats on a local network | NIPS |
| Solution that detects network anomalies | NBA |
| Snort's official description in this task | Full-blown NIPS |
| Training period used by NBA systems to learn normal behavior | Baselining |

## Task 4: First Interaction

| Question | Answer |
|---|---|
| Snort build number | 149 |
| Rules loaded from `/etc/snort/snort.conf` | 4151 |
| Rules loaded from `/etc/snort/snortv2.conf` | 1 |

## Task 5: Sniffing

Snort can monitor network interfaces and inspect packets as they pass through the system. Interface selection and packet capture options determine which traffic is observed.

Example command:

```bash
sudo snort -i eth0
```

Replace `eth0` with the network interface available on the target system.

## Task 6: Packet Logger

| Question | Answer |
|---|---|
| Source port used to connect to port 53 from `145.254.160.237` | 3009 |
| IP ID of the 10th packet in `snort.log.1640048004` | 49313 |
| Referer header of the 4th packet | `http://www.ethereal.com/development.html` |
| ACK number of the 8th packet | `0x38AFFFF3` |
| Number of TCP packets using port 80 | 41 |

## Task 7: IDS/IPS

The HTTP GET rule detects:

```text
2
```

## Task 8: PCAP Investigation

| Question | Answer |
|---|---|
| Alerts generated from `mx-1.pcap` using the default configuration | 170 |
| TCP segments queued | 18 |
| HTTP response headers extracted | 3 |
| Alerts from `mx-1.pcap` using `snortv2.conf` | 68 |
| Alerts from `mx-2.pcap` using the default configuration | 340 |
| TCP packets detected in `mx-2.pcap` | 82 |
| Alerts from `mx-2.pcap` and `mx-3.pcap` using the default configuration | 1020 |

Example command for analyzing a PCAP file:

```bash
sudo snort -r mx-1.pcap -c /etc/snort/snort.conf
```

To use the alternative configuration:

```bash
sudo snort -r mx-1.pcap -c /etc/snort/snortv2.conf
```

The output can vary depending on the configuration file and the packet capture being analyzed.

## Task 9: Snort Rule Structure

| Question | Answer |
|---|---|
| Rule option matching the packet with IP ID 35369 | `TIMESTAMP REQUEST` |
| Number of packets detected by the SYN flag rule | 1 |
| Number of packets detected by the Push-Ack flags rule | 216 |
| UDP packets with the same source and destination IP address | 7 |
| Rule option modified when updating an existing rule | `rev` |

A Snort rule generally contains a rule action, protocol, source and destination addresses, ports, direction, and options. The options define the conditions that trigger an alert or other configured action.

## Key Takeaways

Snort can be used to inspect network traffic, log packets, analyze PCAP files, and detect suspicious activity through rules. Understanding the configuration files and rule syntax is essential when investigating traffic and tuning detection behavior.

This room provided practical experience with packet analysis and the basic workflow of a network intrusion detection and prevention system.
