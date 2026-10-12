# TryHackMe: Tcpdump: The Basics

This write-up covers the Tcpdump: The Basics room on TryHackMe, including the main commands, filtering expressions, packet display options, and answers to the room questions.

## Learning Objectives

- Capture network packets and save them to files.
- Filter packets by host, port, and protocol.
- Use advanced filters, including TCP flags.
- Customize how captured packets are displayed.

## Task 1: Introduction

Question: What is the name of the library that is associated with `tcpdump`?

Answer: `libpcap`

## Task 2: Basic Packet Capture

Question: What option can you add to your command to display addresses only in numeric format?

Answer: `-n`

### Common Tcpdump Options

| Option | Description |
|---|---|
| `-i INTERFACE` | Capture packets on a specific network interface |
| `-w FILE` | Save captured packets to a file |
| `-r FILE` | Read packets from a file |
| `-c COUNT` | Capture a specified number of packets |
| `-n` | Display IP addresses in numeric format |
| `-nn` | Disable IP address and port name resolution |
| `-v`, `-vv`, `-vvv` | Increase output verbosity |

## Task 3: Filtering Expressions

### Common Filters

| Filter | Description |
|---|---|
| `host IP` | Filter packets sent to or received from a host |
| `src host IP` | Filter packets by source host |
| `dst host IP` | Filter packets by destination host |
| `port PORT` | Filter packets by port number |
| `src port PORT` | Filter packets by source port |
| `dst port PORT` | Filter packets by destination port |
| `tcp`, `udp`, `icmp`, `ip`, `ip6` | Filter packets by protocol |
| `and`, `or`, `not` | Combine or negate filtering conditions |

### Command Examples

```bash
sudo tcpdump -i any -nn tcp port 22
sudo tcpdump -i eth0 host example.com and tcp port 443 -w https.pcap
tcpdump -r traffic.pcap src host 192.168.124.1 -nn
```

### Answers

1. Number of packets using the ICMP protocol: `26`
2. IP address of the host that requested the MAC address of `192.168.124.137`: `192.168.124.148`
3. Hostname in the first DNS query: `mirrors.rockylinux.org`

## Task 4: Advanced Filtering

The `greater LENGTH` filter matches packets with a length greater than or equal to the specified value. The `less LENGTH` filter matches packets with a length less than or equal to the specified value.

### TCP Flags

- `tcp-syn`: Synchronize
- `tcp-ack`: Acknowledge
- `tcp-fin`: Finish
- `tcp-rst`: Reset
- `tcp-push`: Push

### Command Examples

```bash
tcpdump -r traffic.pcap 'tcp[tcpflags] == tcp-rst' -nn
tcpdump -r traffic.pcap -nn 'greater 15000'
```

### Answers

1. Number of packets with only the TCP RST flag set: `57`
2. IP address of the host that sent packets larger than 15000 bytes: `185.117.80.53`

## Task 5: Displaying Packets

Question: What is the MAC address of the host that sent an ARP request?

Answer provided: `52:54:00:7c:d3:5b`

### Packet Display Options

| Option | Description |
|---|---|
| `-q` | Display brief packet information |
| `-e` | Include the link-level header and MAC addresses |
| `-A` | Display packet data in ASCII |
| `-xx` | Display packet data in hexadecimal |
| `-X` | Display packet data in hexadecimal and ASCII |

### Command Examples

```bash
tcpdump -r capture.pcap -e
tcpdump -r capture.pcap -A
tcpdump -r capture.pcap -xx
tcpdump -r capture.pcap -X
```

## Task 6: Conclusion

This room introduces the essential Tcpdump commands and filtering techniques used to capture, inspect, and analyze network traffic.

## Reference

[TryHackMe: Tcpdump: The Basics](https://tryhackme.com/room/tcpdump)

Note: Answers that depend on packet capture files should be verified against the current files provided by the TryHackMe lab before being treated as definitive.
