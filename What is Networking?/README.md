# What is Networking?

This room introduces the fundamentals of computer networking and explains how devices communicate with each other.

## Topics Covered

### Networks

A network is a group of devices connected together so they can communicate and share information.

The World Wide Web was invented by Tim Berners-Lee.

### IP Addresses

An IP address is used to identify a device on a network.

IPv4 addresses are divided into four sections called octets. IPv4 uses 32 bits, allowing for 2^32 possible addresses.

IPv6 was created to provide a much larger address space, using 128 bits.

IP addresses can be:

* Public: used to identify devices on the Internet.
* Private: used to identify devices within a private network.

### MAC Addresses

A MAC address stands for Media Access Control.

It is a unique identifier associated with a network interface and is usually represented as twelve hexadecimal characters separated into pairs.

The first part identifies the manufacturer, while the remaining part identifies the device.

MAC spoofing is the process of changing a device's MAC address to make it appear as another device.

### Ping and ICMP

Ping is a network utility used to test connectivity between devices.

It uses ICMP (Internet Control Message Protocol) packets.

A ping sends an ICMP Echo Request and waits for an ICMP Echo Reply. The response time can be used to measure the latency between the devices.

Basic syntax:

```bash
ping 10.10.10.10
```

The `-c` option can be used on Linux to specify how many packets should be sent:

```bash
ping -c 4 10.10.10.10
```

Important information shown by ping includes:

* Packet loss
* Response time
* TTL
* Number of packets transmitted and received

## Conclusion

This room introduced the basic concepts needed to understand computer networking, including networks, IP addresses, MAC addresses, MAC spoofing, ICMP, and the ping utility.

These concepts provide a foundation for learning more advanced networking and cybersecurity topics.
