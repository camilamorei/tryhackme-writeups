# Protocols and Servers 2

## Overview

This room explores common network attacks against communication protocols and introduces security mechanisms designed to protect data transmission.

It focuses on network sniffing, Man-in-the-Middle (MITM) attacks, Transport Layer Security (TLS), Secure Shell (SSH), and password attacks.

## Topics Covered

- Sniffing Attacks
- Man-in-the-Middle (MITM) Attacks
- Transport Layer Security (TLS)
- Secure Shell (SSH)
- Password Attacks
- Hydra

## Tools and Commands

### Tcpdump

Tcpdump is a command-line packet analyzer used to capture and inspect network traffic.

Capture Telnet traffic:

```bash
sudo tcpdump port 23
```

### Wireshark

Wireshark is a graphical network protocol analyzer used to inspect captured packets.

Display only IMAP traffic using the following filter:

```text
imap
```

### Ettercap

Ettercap is a network security tool used for network traffic analysis and Man-in-the-Middle attacks.

It provides different interfaces for interacting with network traffic.

### Bettercap

Bettercap is a powerful framework used for network reconnaissance, traffic analysis, and Man-in-the-Middle testing.

### TLS

Transport Layer Security (TLS) provides encryption and authentication for network communications.

It protects data against interception and unauthorized modification.

DNS over TLS (DoT) uses TLS to encrypt DNS queries.

### SSH

Secure Shell (SSH) provides encrypted remote access to systems.

Connect to a remote machine:

```bash
ssh username@MACHINE_IP
```

Check the remote kernel release:

```bash
uname -r
```

Transfer files from a remote machine using SCP:

```bash
scp username@MACHINE_IP:/path/to/file .
```

### Hydra

Hydra is a password auditing tool that performs authentication testing against network services using username and password lists.

Example of an IMAP authentication test in an authorized lab:

```bash
hydra -l username -P wordlist.txt MACHINE_IP imap
```

## Key Takeaways

- Network sniffing allows captured traffic to be inspected.
- Unencrypted protocols can expose sensitive information.
- MITM attacks can intercept or modify communications.
- TLS protects data confidentiality and integrity through encryption.
- SSH is a secure alternative to Telnet for remote administration.
- Hydra can be used to evaluate password strength and authentication security.

## Conclusion

This room demonstrates how attackers exploit weaknesses in network communication and authentication mechanisms. Understanding these techniques helps identify insecure configurations and implement stronger security controls.
