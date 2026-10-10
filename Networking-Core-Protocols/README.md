# Networking Core Protocols

## Overview

This room explores fundamental networking protocols and how they work behind the scenes. It focuses on using command-line tools such as `telnet` to interact directly with network services and understand how clients communicate with servers.

## Protocols Covered

### DNS (Domain Name System)

DNS translates domain names into IP addresses and supports different record types.

- `A`: Maps a domain name to an IPv4 address.
- `AAAA`: Maps a domain name to an IPv6 address.
- `MX`: Identifies mail servers for a domain.

### WHOIS

WHOIS provides information about domain registrations, including registration dates and registrar details.

### HTTP (Hypertext Transfer Protocol)

HTTP is used to request and deliver web resources. It operates over TCP port 80 by default.

Using Telnet, a client can manually send HTTP requests and inspect the server's response.

### FTP (File Transfer Protocol)

FTP is used to transfer files between clients and servers. Its default control port is TCP 21.

Useful commands include:

- `USER`: Specifies the username.
- `PASS`: Provides the password.
- `LIST`: Lists directory contents.
- `RETR`: Downloads a file.
- `QUIT`: Ends the session.

### SMTP (Simple Mail Transfer Protocol)

SMTP is used to send email messages between clients and mail servers.

Important commands include:

- `HELO` or `EHLO`: Introduces the client to the server.
- `MAIL FROM`: Specifies the sender.
- `RCPT TO`: Specifies the recipient.
- `DATA`: Begins the email message body.
- `.` on a separate line: Marks the end of the message.
- `QUIT`: Ends the session.

### POP3 (Post Office Protocol version 3)

POP3 is used to retrieve email from a mail server. Its default port is TCP 110.

Common commands include:

- `USER`: Specifies the username.
- `PASS`: Authenticates the user.
- `LIST`: Lists available messages.
- `RETR`: Retrieves a message.
- `QUIT`: Ends the session.

POP3 is commonly associated with downloading messages to a client, potentially removing them from the server depending on client behavior and configuration.

### IMAP (Internet Message Access Protocol)

IMAP allows email messages and mailbox changes to be synchronized across multiple devices. Its default port is TCP 143.

Important commands include:

- `LOGIN`: Authenticates the user.
- `SELECT`: Selects a mailbox.
- `FETCH`: Retrieves message data.
- `MOVE`: Moves messages to another mailbox.
- `COPY`: Copies messages to another mailbox.
- `LOGOUT`: Ends the session.

Unlike typical POP3 usage, IMAP generally keeps messages on the server and synchronizes mailbox state between clients.

## Default Ports Reference

| Protocol | Transport | Default Port |
|---|---|---:|
| TELNET | TCP | 23 |
| DNS | UDP/TCP | 53 |
| HTTP | TCP | 80 |
| HTTPS | TCP | 443 |
| FTP | TCP | 21 |
| SMTP | TCP | 25 |
| POP3 | TCP | 110 |
| IMAP | TCP | 143 |

## Practical Skills

During this room, I practiced interacting with network services through Telnet and learned how to:

- Understand DNS record types and domain registration information.
- Send HTTP requests and inspect server responses.
- Authenticate to FTP and retrieve files.
- Compose and send email through SMTP commands.
- Authenticate to POP3 and retrieve messages.
- Use IMAP commands to select mailboxes and fetch email messages.
- Identify common protocol ports and understand their purposes.

## Key Takeaways

Understanding application-layer protocols helps explain how network services operate beyond graphical interfaces. Interacting with services directly makes it easier to understand their request and response formats, authentication mechanisms, and communication workflows.

This knowledge is useful for troubleshooting, network administration, and cybersecurity analysis.

## Conclusion

Networking Core Protocols provided hands-on experience with several essential networking protocols. Learning how to interact with these services from the command line establishes a foundation for studying secure protocols, network traffic analysis, and defensive security.
