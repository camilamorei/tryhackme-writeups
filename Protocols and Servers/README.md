# Protocols and Servers

## Overview

This room explores common network protocols and their respective services, focusing on how they operate, which ports they use, and how to interact with them during network reconnaissance and penetration testing.

## Topics Covered

- Telnet
- Hypertext Transfer Protocol (HTTP)
- File Transfer Protocol (FTP)
- Simple Mail Transfer Protocol (SMTP)
- Post Office Protocol 3 (POP3)
- Internet Message Access Protocol (IMAP)

## Protocols and Default Ports

| Protocol | Port | Purpose |
|---|---:|---|
| Telnet | 23 | Remote terminal access |
| HTTP | 80 | Web communication |
| FTP | 21 | File transfer |
| SMTP | 25 | Email transmission |
| POP3 | 110 | Email retrieval |
| IMAP | 143 | Email access and synchronization |

## Tools and Commands

### Telnet

Telnet provides remote terminal access over TCP. Its communication is unencrypted, meaning credentials and other transmitted data can be intercepted.

```bash
telnet MACHINE_IP
```

Telnet can also be used to manually interact with other TCP services.

### HTTP

HTTP is an application-layer protocol used for communication between web clients and servers.

Connect to a web server using Telnet:

```bash
telnet MACHINE_IP 80
```

### FTP

FTP is a protocol designed for transferring files between a client and a server.

Connect using:

```bash
ftp MACHINE_IP
```

### SMTP

SMTP is responsible for sending emails between clients and mail servers.

Connect to the SMTP service:

```bash
telnet MACHINE_IP 25
```

### POP3

POP3 is an email retrieval protocol that allows clients to download messages from a mail server.

Connect using:

```bash
telnet MACHINE_IP 110
```

Useful POP3 commands:

```text
USER username
PASS password
STAT
LIST
RETR 1
QUIT
```

### IMAP

IMAP allows users to access and synchronize emails stored on a remote mail server.

Default port: 143.

Connect using:

```bash
telnet MACHINE_IP 143
```

## Key Takeaways

- Different network services operate on specific TCP ports.
- Telnet can be used to manually interact with text-based network protocols.
- FTP, POP3, and Telnet may expose sensitive information when configured without encryption.
- SMTP is used for email transmission, while POP3 and IMAP are used for email retrieval and access.
- Identifying open ports and understanding their associated services is an important part of network reconnaissance.

## Conclusion

This room introduced several fundamental application-layer protocols and demonstrated how to interact with network services using command-line tools. Understanding these protocols is essential for network reconnaissance, service enumeration, and penetration testing.
