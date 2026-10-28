# NetworkMiner

## Overview

NetworkMiner is an open-source Network Forensic Analysis Tool (NFAT) developed by Netresec. It can analyze live traffic and packet capture files to identify hosts, sessions, protocols, credentials, transferred files, and other useful evidence.

NetworkMiner is especially useful for quickly reviewing PCAP files and extracting information before conducting a deeper investigation with tools such as Wireshark or tcpdump.

## Task 1: Room Introduction

This task introduces NetworkMiner and explains the lab environment.

## Task 2: NetworkMiner in Forensics

Network forensics involves investigating network traffic to identify suspicious activity, security breaches, and network anomalies.

NetworkMiner can help analysts identify:

- IP addresses, MAC addresses, hostnames, and operating systems.
- Network sessions, services, and open ports.
- Potential attack indicators, including scanning and spoofing.
- Credentials, files, images, emails, and other extracted data.

The main data types used in network forensics are live traffic, traffic captures, and log files.

## Task 3: What is NetworkMiner?

NetworkMiner provides several capabilities:

- Traffic sniffing and packet capture.
- PCAP parsing and protocol analysis.
- Operating system fingerprinting.
- File, image, and email extraction.
- Credential discovery.
- Cleartext keyword and string extraction.

NetworkMiner has two main operating modes:

- Sniffer mode: Captures traffic from a network interface. This feature is available on Windows.
- Packet parsing mode: Processes captured traffic for offline investigation.

NetworkMiner is useful for quickly identifying relevant information. Wireshark is generally better suited for detailed packet decoding, filtering, protocol analysis, and payload investigation.

## Task 4: Tool Overview 1

### File: mx-3.pcap

Answers:

- Total number of frames: `460`
- IP addresses sharing a MAC address with host `145.253.2.203`: `2`
- Packets sent from host `65.208.228.223`: `72`
- Web server banner: `Apache`

### File: mx-4.pcap

Answers:

- Extracted username for host `02694W-WIN10`: `#B\Administrator`
- Extracted password field: NTLMv2 response hash

The full extracted hash is:

```text
$NETNTLMv2$#B$136B077D942D9A63$FBFF3C253926907AAAAD670A9037F2A5$01010000000000000094D71AE38CD60170A8D571127AE49E00000000020004003300420001001E003000310035003600360053002D00570049004E00310036002D004900520004001E0074006800720065006500620065006500730063006F002E0063006F006D0003003E003000310035003600360073002D00770069006E00310036002D00690072002E0074006800720065006500620065006500730063006F002E0063006F006D0005001E0074006800720065006500620065006500730063006F002E0063006F006D00070008000094D71AE38CD601060004000200000008003000300000000000000000000000003000009050B30CECBEBD73F501D6A2B88286851A6E84DDFAE1211D512A6A5A72594D340A001000000000000000000000000000000000000900220063006900660073002F003100370032002E00310036002E00360036002E0033003600000000000000000000000000
```

## Task 5: Tool Overview 2

### File: mx-7.pcap

Answers:

- Linux distribution mentioned in the extracted file: `CentOS`
- Name and surname mentioned in the file associated with frame `76469`, or frame `75942`: `Ned Flanders`
- Source address of `ads.bmp.2E5F0FD9[1].bmp`: `80.239.178.187`
- Frame number of the possible TLS anomaly: `36255`

### File: mx-9

Answers:

- Platform that sent an email with a subject starting with "You have more...": `Facebook`
- Email address of Branson Matheson: `branson@sandsite.org`

## Task 6: Version Differences

NetworkMiner versions can differ in the information they extract and display.

Answers:

- Version that can detect duplicate MAC addresses: `2.7`
- Version that can handle frames: `1.6`
- Version that provides more detailed packet information: `1.6`

## Task 7: Exercises

### File: case1.pcap

Answers:

- Full operating system name of host `131.151.37.122`: `Windows - Windows NT 4`
- Bytes sent by client `131.151.32.91` through port `1065`: `192`
- Bytes sent back by server `131.151.37.122` through port `143`: `20769`
- Sequence number of frame `9`: `2AD77400`
- Number of detected content types: `2`

### File: case2.pcap

Answers:

- USB product brand: `ASIX`
- Phone model: `Lumia 535`
- Source IP address of the fish image: `50.22.95.9`
- Password for `homer.pwned.se@gmx.com`: `spring2015`
- DNS query in frame `62001`: `pop.gmx.com`

## Task 8: Conclusion

NetworkMiner provides a convenient way to investigate packet capture files and extract useful information. It can quickly identify hosts, sessions, credentials, files, images, and messages associated with network activity.

The recommended workflow is to use NetworkMiner for an initial overview and extraction of relevant information, then continue with Wireshark or tcpdump for more detailed packet-level analysis.

## Key Takeaways

- NetworkMiner is a network forensic analysis tool, not a replacement for a dedicated packet analyzer.
- PCAP parsing can reveal hosts, sessions, protocols, files, and credentials.
- The Hosts, Sessions, DNS, Credentials, Files, Parameters, Keywords, Messages, and Anomalies tabs provide different perspectives on captured traffic.
- Version differences affect the details NetworkMiner can process and display.
- Extracted information should be correlated with packet-level evidence before drawing conclusions.
- Sensitive data such as credentials and password hashes should be handled securely.
