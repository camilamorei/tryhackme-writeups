# Packets & Frames

TryHackMe room covering how data is transmitted across networks using packets, frames, TCP, UDP, IP addresses, and ports.

## Topics Covered

* Packets and Frames
* TCP/IP model
* TCP
* Three-way handshake
* UDP
* IP addressing
* Network ports
* Common protocols and ports
* Encapsulation and decapsulation

## Tasks

### Task 1 — Packets & Frames

A **packet** is Layer 3 data that contains IP addressing information.

A **frame** is Layer 2 data that encapsulates the packet and contains information such as MAC addresses.

Answers:

* Data with IP addressing information: `Packet`
* Data without IP addressing information: `Frame`

### Task 2 — TCP

TCP stands for **Transmission Control Protocol**.

TCP is connection-based and uses a three-way handshake before transmitting data.

The three-way handshake consists of:

1. `SYN`
2. `SYN/ACK`
3. `ACK`

The TCP header also contains a **Checksum**, which is used to verify the integrity of the data.

Answers:

* TCP header field used to ensure integrity: `Checksum`
* Three-way handshake: `SYN → SYN/ACK → ACK`

### Task 3 — TCP Three-Way Handshake

This task provided a practical challenge where the TCP handshake packets had to be placed in the correct order.

Correct order:

```text
SYN
SYN/ACK
ACK
```

After completing the challenge, the site provides a flag.

### Task 4 — UDP/IP

UDP stands for **User Datagram Protocol**.

Unlike TCP, UDP is stateless and does not establish a connection using a three-way handshake.

Answers:

* UDP: `User Datagram Protocol`
* Connection type: `Stateless`
* File transfer: `TCP`
* Video call: `UDP`

UDP is useful for applications such as video calls where speed is more important than guaranteeing that every packet arrives.

### Task 5 — Ports 101

Network ports are numerical values ranging from `0` to `65535`.

Common ports include:

| Protocol | Port | Description             |
| -------- | ---: | ----------------------- |
| FTP      |   21 | File Transfer Protocol  |
| SSH      |   22 | Secure Shell            |
| HTTP     |   80 | Web traffic             |
| HTTPS    |  443 | Encrypted web traffic   |
| SMB      |  445 | File and device sharing |
| RDP      | 3389 | Remote Desktop Protocol |

The practical challenge required connecting to:

```text
8.8.8.8:1234
```

The challenge provides the flag after connecting successfully.

### Task 6 — Extending Your Network

The final task required terminating the static site lab used in the previous practical challenges.

After terminating the lab, the task can be checked and the next room, **Extending Your Network**, can be started.

## What I Learned

This room helped me understand how data moves through a network at a more practical level.

I learned the difference between packets and frames, how TCP establishes connections using the three-way handshake, how UDP differs from TCP, and how ports are used to identify network services.

I also learned some of the most common ports used by protocols such as FTP, SSH, HTTP, HTTPS, SMB, and RDP.

## Key Takeaways

* Packets operate at Layer 3 and contain IP addressing information.
* Frames operate at Layer 2 and encapsulate packets.
* TCP is connection-oriented and uses a three-way handshake.
* UDP is stateless and does not perform a three-way handshake.
* Ports range from `0` to `65535`.
* Common services are associated with standard ports.
* A service can run on a non-standard port, but the port must be specified when connecting.
