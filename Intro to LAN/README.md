# Intro to LAN

This room introduces the fundamentals of Local Area Networks (LANs) and how devices communicate within them.

## Topics Covered

### LAN Topologies

A network topology describes the design or structure of a network.

The main topologies covered in this room are:

* Star topology
* Bus topology
* Ring topology

#### Star Topology

In a star topology, devices are individually connected to a central networking device such as a switch or hub.

Advantages include:

* Easy to scale
* More reliable than some other topologies
* Easy to add new devices

Disadvantages include:

* More expensive to set up
* Requires more cabling
* The central device can become a single point of failure

#### Bus Topology

A bus topology connects devices through a single backbone cable.

Advantages include:

* Low cost
* Easy to set up
* Requires less networking equipment

Disadvantages include:

* Can become a bottleneck
* Difficult to troubleshoot
* The backbone cable is a single point of failure

#### Ring Topology

In a ring topology, devices are connected together in a loop. Data travels around the network until it reaches its destination.

It requires less cabling than a star topology, but a failure in a device or connection can affect the entire network.

### Switches

A switch connects multiple devices on a local network.

Unlike a hub, a switch keeps track of which device is connected to each port and can forward traffic directly to the intended device.

This reduces unnecessary network traffic.

### Routers

A router connects different networks and forwards data between them.

The process of creating a path for data to travel between networks is called routing.

### Subnetting

Subnetting is the process of dividing a network into smaller networks.

A subnet mask is used to determine which part of an IP address identifies the network and which part identifies the host.

Subnets use addresses for:

* Network identification
* Host identification
* Default gateway

Subnetting can improve network efficiency, security, and control.

### ARP

ARP stands for Address Resolution Protocol.

It is used to associate an IP address with a MAC address on a local network.

ARP uses two main message types:

* Request
* Reply

An ARP Request asks which device owns a particular IP address. The corresponding device responds with an ARP Reply containing its MAC address.

Devices store these mappings in an ARP cache.

### DHCP

DHCP stands for Dynamic Host Configuration Protocol.

It allows devices to automatically receive IP configuration when connecting to a network.

The basic DHCP process is:

1. DHCP Discover
2. DHCP Offer
3. DHCP Request
4. DHCP ACK

This allows a device to obtain and use an IP address without manually configuring it.

## Conclusion

This room introduced important LAN concepts including network topologies, switches, routers, subnetting, ARP, and DHCP.

Understanding these concepts provides a foundation for learning how devices communicate across local and larger networks.
