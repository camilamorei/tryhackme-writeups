# Firewall Fundamentals - TryHackMe

## About the Lab

This room introduces the fundamentals of firewalls and explains how they protect networks and devices by monitoring and controlling incoming and outgoing traffic.

Platform: TryHackMe  
Category: Cybersecurity  
Topic: Network Security  
Status: Completed

## Learning Objectives

- Understand how firewalls work.
- Learn about different types of firewalls.
- Understand firewall rules and their components.
- Practice using Windows Defender Firewall.
- Explore firewall utilities in Linux.
- Learn basic UFW commands.

## 1. What Is a Firewall?

A firewall is a security solution that monitors and controls incoming and outgoing network traffic based on predefined security rules.

It acts as a digital security guard, allowing authorized connections and blocking unauthorized traffic.

## 2. Types of Firewalls

| Type | Description |
|---|---|
| Stateless Firewall | Filters packets without tracking the state of connections. |
| Stateful Firewall | Tracks active connections and their states. |
| Proxy Firewall | Acts as an intermediary and can inspect application traffic. |
| Next Generation Firewall (NGFW) | Provides advanced traffic inspection and threat prevention capabilities. |

### OSI Model Layers

- Layers 3 and 4: Stateless and Stateful Firewalls.
- Layer 7: Proxy Firewall.
- Layers 3 to 7: Next Generation Firewall.

## 3. Firewall Rules

A firewall rule consists of several components:

- Source Address: The IP address from which traffic originates.
- Destination Address: The IP address receiving the traffic.
- Port: The port used for communication.
- Protocol: The communication protocol, such as TCP or UDP.
- Action: The operation performed on matching traffic.
- Direction: Specifies whether the rule applies to incoming or outgoing traffic.

### Main Actions

- Allow: Permits the specified traffic.
- Deny: Blocks the specified traffic.
- Forward: Redirects traffic to another destination.

### Traffic Directions

- Inbound: Incoming traffic.
- Outbound: Outgoing traffic.
- Forward: Traffic redirected between network segments.

## 4. Windows Defender Firewall

Windows Defender Firewall is the built in firewall included with Windows.

It allows administrators to create custom rules to control incoming and outgoing network connections.

### Network Profiles

- Private: Trusted networks, such as a home network.
- Public: Public or untrusted networks, such as public WiFi.

### Practical Example: Blocking HTTP and HTTPS

An outbound rule can block TCP traffic destined for ports 80 and 443.

- Port 80: HTTP.
- Port 443: HTTPS.

This can prevent access to websites that rely on these connections, although other services and ports may remain accessible.

## 5. Linux Firewalls

Linux provides several utilities for managing firewall rules.

| Utility | Description |
|---|---|
| Netfilter | A packet filtering framework in the Linux kernel. |
| iptables | A traditional utility for configuring firewall rules. |
| nftables | The successor to iptables, providing modern packet filtering capabilities. |
| firewalld | A firewall management utility that uses predefined zones and configurations. |
| UFW | A simplified interface for managing firewall rules. |

## 6. Basic UFW Commands

### Check Firewall Status

```bash
sudo ufw status
```

### Enable the Firewall

```bash
sudo ufw enable
```

### Allow All Outgoing Traffic by Default

```bash
sudo ufw default allow outgoing
```

### Deny All Outgoing Traffic by Default

```bash
sudo ufw default deny outgoing
```

### Block Incoming SSH Traffic

```bash
sudo ufw deny 22/tcp
```

### List Numbered Rules

```bash
sudo ufw status numbered
```

### Delete a Rule

```bash
sudo ufw delete NUMBER
```

Replace NUMBER with the number of the rule you want to delete.

## 7. Lab Questions and Answers

| Question | Answer |
|---|---|
| Which security solution inspects incoming and outgoing traffic? | Firewall |
| Which firewall maintains the state of connections? | Stateful Firewall |
| Which firewall offers heuristic traffic analysis? | Next Generation Firewall (NGFW) |
| Which firewall inspects traffic destined for an application? | Proxy Firewall |
| Which action permits traffic? | Allow |
| What is the direction of traffic leaving a network? | Outbound |
| Which Linux utility is considered the successor to iptables? | nftables |
| Which UFW rule denies all outgoing traffic by default? | `ufw default deny outgoing` |

## 8. Key Takeaways

This lab introduced the fundamental concepts of firewalls and their role in network security.

I learned the differences between stateless, stateful, proxy, and next generation firewalls. I also explored firewall rules, network traffic directions, Windows Defender Firewall, and Linux firewall utilities.

These concepts provide a foundation for further studies in network security, traffic analysis, and cybersecurity.

## 9. Next Steps

- Study networking fundamentals.
- Practice configuring firewall rules on Linux.
- Learn network traffic analysis using Wireshark.
- Study ports, TCP, UDP, and SSH.
- Continue completing cybersecurity labs on TryHackMe.

Note: This README documents the concepts and exercises covered in the lab. Practical results may vary depending on the system and its configuration.
