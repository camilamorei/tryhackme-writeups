# Extending Your Network

TryHackMe room covering port forwarding, firewalls, VPNs, routers, switches, VLANs, and network simulation.

## Topics Covered

* Port forwarding
* Firewalls
* Stateful and stateless firewalls
* VPNs
* PPP, PPTP and IPSec
* Routers
* Switches
* VLANs
* TCP handshakes
* Network simulation

## Tasks

### Task 1 — Introduction to Port Forwarding

Port forwarding allows applications and services inside a private network to be accessed from the Internet.

Port forwarding is configured on the **router**.

Answer:

* Device used to configure port forwarding: `Router`

### Task 2 — Firewalls 101

A firewall determines which network traffic is allowed or denied based on factors such as:

* Source IP
* Destination IP
* Port
* Protocol

Firewalls perform packet inspection to make these decisions.

Answers:

* OSI layers: `3 & 4`
* Firewall that inspects the entire connection: `Stateful`
* Firewall that inspects individual packets: `Stateless`

### Task 3 — Practical: Firewall

The practical challenge required blocking malicious traffic while allowing legitimate traffic to reach the web server.

The malicious traffic originated from:

```text
198.51.100.34
```

The web server was:

```text
203.0.110.1
```

The traffic used port:

```text
80
```

The firewall rule used was:

| Source IP       | Destination IP | Port | Action |
| --------------- | -------------- | ---: | ------ |
| `198.51.100.34` | `203.0.110.1`  | `80` | `DROP` |

This blocks the malicious HTTP traffic without blocking the legitimate traffic.

### Task 4 — VPN Basics

A VPN creates a secure tunnel between devices or networks over the Internet.

VPNs can provide:

* Secure communication between different networks
* Privacy through encryption
* Anonymity depending on the VPN provider and its privacy practices

VPN technologies covered in the room include:

* PPP
* PPTP
* IPSec

Answers:

* Technology that provides encryption and authentication of data: `PPP`
* Technology that uses the IP framework: `IPSec`

### Task 5 — LAN Networking Devices

#### Router

A router connects different networks and forwards data between them.

Routers operate at **Layer 3** of the OSI model and can be configured for functions such as:

* Routing
* Port forwarding
* Firewall rules

The action performed by a router is called **routing**.

#### Switch

A switch connects multiple devices within a network.

Layer 2 switches forward frames using MAC addresses.

Layer 3 switches can also perform routing using IP addresses.

The two switch layers covered in the room are:

```text
Layer 2,Layer 3
```

#### VLAN

A VLAN, or Virtual Local Area Network, allows devices on the same physical network to be logically separated.

This can improve network security by controlling how different groups of devices communicate.

### Task 6 — Practical: Network Simulator

The practical challenge used a network simulator to show how a packet travels through a network.

The topology included:

```text
computer1 → switch1 → router → switch2 → computer3
```

A TCP packet was sent from `computer1` to `computer3`.

The simulator displayed the steps taken by the packet, including ARP traffic and the TCP handshake.

The Network Log contained:

```text
5
```

`HANDSHAKE` entries.

The flag is intentionally not included in this writeup.

## What I Learned

This room helped me understand how different networking technologies work together.

I learned how routers perform routing and port forwarding, how firewalls control network traffic, and how VPNs create secure tunnels between networks.

I also learned the difference between Layer 2 and Layer 3 switches and how VLANs can be used to separate devices within the same physical network.

The network simulator was useful for visualizing how a TCP connection is established and how packets move through switches and routers.

## Key Takeaways

* Port forwarding is configured on a router.
* Firewalls can inspect and filter network traffic.
* Stateful firewalls track entire connections.
* Stateless firewalls inspect individual packets.
* VPNs create secure tunnels between networks.
* Routers operate at Layer 3.
* Layer 2 switches use MAC addresses to forward frames.
* Layer 3 switches can perform routing.
* VLANs provide logical network segmentation.
* TCP uses a handshake to establish a connection.
