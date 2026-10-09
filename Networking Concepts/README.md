# Networking Concepts

## Introduction

This room introduces the fundamental concepts of computer networking, including the ISO OSI model, the TCP/IP model, IP addressing, subnets, transport protocols, encapsulation, and remote communication using Telnet.

Understanding these concepts is essential for cybersecurity because network traffic analysis, troubleshooting, and security monitoring rely on knowing how devices communicate and how data travels across networks.

## Task 1: Introduction

This task introduced the basic concepts of computer networking and explained why understanding network communication is important.

## Task 2: OSI Model

The ISO OSI model divides network communication into seven layers. Each layer has specific responsibilities.

The seven layers, from top to bottom, are:

1. Application
2. Presentation
3. Session
4. Transport
5. Network
6. Data Link
7. Physical

Key concepts covered:

* The Transport Layer (Layer 4) provides end-to-end communication between applications.
* The Network Layer (Layer 3) handles routing packets between networks.
* The Presentation Layer (Layer 6) handles data representation and encoding.
* The Data Link Layer (Layer 2) manages communication between devices on the same network segment.

## Task 3: TCP/IP Model

The TCP/IP model is an implemented networking model developed in the 1970s. It groups networking functions into four layers.

The four layers are:

1. Application
2. Transport
3. Internet
4. Link

The TCP/IP Application Layer combines the responsibilities of the OSI Application, Presentation, and Session layers.

Examples of protocols covered:

* Application: HTTP, HTTPS, FTP, SSH, SMTP, and DNS
* Transport: TCP and UDP
* Internet: IP and ICMP
* Link: Ethernet and Wi-Fi

Answers:

* HTTP belongs to the Application Layer.
* The TCP/IP Application Layer covers three OSI layers.

## Task 4: IP Addresses and Subnets

An IP address identifies a device on a network and allows it to communicate with other devices.

### IPv4

An IPv4 address consists of 32 bits divided into four octets. Each octet represents a decimal value between 0 and 255.

Example: `192.168.1.10`

Important concepts:

* Network address: identifies a network.
* Broadcast address: sends traffic to all hosts on a subnet.
* Subnet mask: identifies the network and host portions of an IP address.
* CIDR notation: represents a subnet prefix, such as `/24`.
* Routing: forwards packets toward their destination network.

### Private IP Address Ranges

The private IPv4 ranges defined by RFC 1918 are:

| Range                         | CIDR           |
| ----------------------------- | -------------- |
| 10.0.0.0 – 10.255.255.255     | 10.0.0.0/8     |
| 172.16.0.0 – 172.31.255.255   | 172.16.0.0/12  |
| 192.168.0.0 – 192.168.255.255 | 192.168.0.0/16 |

Private IP addresses are generally used within local networks. Network Address Translation (NAT) allows devices using private addresses to access external networks through a public IP address.

Useful commands:

Windows:

```bash
ipconfig
```

Linux:

```bash
ip address show
```

Short form:

```bash
ip a s
```

Answers:

* IP address that is not private: `49.69.147.197`
* Invalid IPv4 address: `192.168.305.19`

## Task 5: UDP and TCP

TCP and UDP are transport-layer protocols that use port numbers to identify applications or services on a host.

### UDP

User Datagram Protocol (UDP) is connectionless. It sends data without establishing a connection or guaranteeing delivery.

Characteristics:

* Connectionless communication
* No built-in delivery acknowledgment
* Low overhead
* Commonly used when speed and low latency are important

### TCP

Transmission Control Protocol (TCP) is connection-oriented and provides reliable data delivery.

Characteristics:

* Establishes a connection before data transfer
* Uses sequence numbers and acknowledgments
* Detects missing or duplicated data
* Uses a three-way handshake to establish a connection

The TCP three-way handshake consists of:

1. SYN
2. SYN-ACK
3. ACK

TCP and UDP use port numbers ranging from 0 to 65535, although port 0 is reserved.

Answers:

* Protocol that requires a three-way handshake: TCP
* Approximate number of port numbers: 65,000

## Task 6: Encapsulation

Encapsulation occurs when each networking layer adds its own protocol information to the data received from the layer above it.

The data units are:

1. Application Layer: Application data
2. Transport Layer: TCP segment or UDP datagram
3. Internet Layer: IP packet
4. Link Layer: Ethernet or Wi-Fi frame

At the receiving end, decapsulation reverses this process, removing the relevant headers and trailer until the original application data is recovered.

Answers:

* An IP packet transmitted over Wi-Fi is encapsulated within a frame.
* UDP data unit: Datagram
* TCP data unit: Segment

## Task 7: Telnet

Telnet is a protocol and command-line client that can establish text-based connections to remote systems over TCP.

The room demonstrated connections to three services:

| Service | Default TCP Port | Purpose                           |
| ------- | ---------------: | --------------------------------- |
| Echo    |                7 | Returns the received text         |
| Daytime |               13 | Returns the current date and time |
| HTTP    |               80 | Serves web pages                  |

Telnet can also be used to interact manually with services listening on TCP ports. For example, an HTTP request can be sent by connecting to port 80 and entering the request line and the Host header.

Example:

```bash
telnet MACHINE_IP 80
```

HTTP request:

```http
GET / HTTP/1.1
Host: telnet.thm
```

Security note: Telnet does not encrypt its communication. For remote administration, SSH is generally preferred because it provides encrypted communication.

Answers:

* HTTP server: `lighttpd/1.4.63`
* Flag: `THM{TELNET_MASTER}`

## Task 8: Conclusion

This room covered the fundamental concepts required to understand network communication.

Key takeaways:

* The OSI and TCP/IP models organize networking functions into layers.
* IP addresses identify hosts, while subnets define network boundaries.
* Routers forward packets between networks.
* TCP provides reliable, connection-oriented communication, while UDP is connectionless.
* Encapsulation allows each networking layer to add the information required for data delivery.
* Telnet can be used to communicate with TCP services, but it does not provide encryption.

## Tools and Commands

* `ipconfig`
* `ifconfig`
* `ip address show`
* `telnet`
* `nc` (Netcat)

## Learning Outcomes

After completing this room, I gained a better understanding of network layers, IPv4 addressing, private IP ranges, subnet masks, routing, TCP and UDP, encapsulation, and basic interaction with network services.

These concepts provide a foundation for further studies in network security, traffic analysis, and defensive security.

## References

* TryHackMe: Networking Concepts
* RFC 1122: Requirements for Internet Hosts — Communication Layers
* RFC 1918: Address Allocation for Private Internets
