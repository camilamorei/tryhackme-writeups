# Operating System Security

## Introduction

This room introduces the fundamentals of operating system security and common weaknesses that can affect confidentiality, integrity, and availability.

The room also provides a practical example of attacking a Linux system by exploiting weak passwords and poor security practices.

## Task 1 - Introduction to Operating System Security

An operating system acts as a layer between computer hardware and applications. It allows software to interact with hardware according to specific rules.

Examples of operating systems include:

* Windows
* macOS
* Linux
* Android
* iOS
* Chrome OS
* AIX
* Solaris

Operating system security is important because computers and mobile devices can contain sensitive information such as:

* Private conversations
* Personal photos
* Emails
* Saved passwords
* Banking information
* Confidential work or university files

Security can be divided into three main principles:

* Confidentiality - Ensuring that private information is only accessible to authorized people.
* Integrity - Preventing unauthorized modification of files and information.
* Availability - Ensuring that systems and data remain accessible when needed.

The answer to the task question was:

```text
Thunderbird
```

Thunderbird is an email client, not an operating system.

## Task 2 - Common Examples of OS Security

This task covered three common weaknesses related to operating system security:

* Authentication and weak passwords
* Weak file permissions
* Malicious programs

### Authentication and Weak Passwords

Authentication verifies the identity of a user.

There are three common authentication factors:

* Something you know - Password or PIN
* Something you are - Fingerprint or other biometric information
* Something you have - Phone or security device

Weak and reused passwords can make accounts easier to compromise.

Examples of common weak passwords include:

* `123456`
* `123456789`
* `qwerty`
* `password`
* `111111`
* `12345678`
* `abc123`

The strong password identified in the task was:

```text
LearnM00r
```

### Weak File Permissions

The principle of least privilege means that users should only have access to the files and resources they actually need.

Weak file permissions can affect:

* Confidentiality - Unauthorized users may be able to read sensitive files.
* Integrity - Unauthorized users may be able to modify files.

Proper file permissions help reduce the impact of unauthorized access.

### Malicious Programs

Malicious programs can affect all three security principles.

For example:

* Trojan horses can give attackers access to a system.
* Malware can allow attackers to read or modify files.
* Ransomware can encrypt files and prevent users from accessing them.

Ransomware mainly affects availability because the victim loses access to their files until they are recovered or decrypted.

## Task 3 - Practical Example of OS Security

The practical part of the room involved accessing a Linux machine through SSH and exploiting weak passwords.

### Connecting to the Lab Machine

The target machine IP was:

```text
10.67.175.148
```

The attacker machine was connected through the TryHackMe AttackBox.

The first user targeted was `johnny`.

The SSH command was:

```bash
ssh johnny@10.67.175.148
```

### Finding Johnny's Password

The password was discovered by trying the common passwords from the previous task.

The password for `johnny` was:

```text
abc123
```

After logging in, the current user was verified with:

```bash
whoami
```

The result was:

```text
johnny
```

### Finding the Root Password

The `history` command was used to inspect commands previously entered by Johnny:

```bash
history
```

The command history contained the root password:

```text
happyHack!NG
```

The password had been accidentally entered directly into the terminal.

### Switching to Root

The root account was accessed with:

```bash
su - root
```

The discovered password was entered:

```text
happyHack!NG
```

The current user could then be verified with:

```bash
whoami
```

The result was:

```text
root
```

### Reading the Root Flag

After obtaining root privileges:

```bash
cd /root
ls
```

The flag file was located and read with:

```bash
cat flag.txt
```

The output of this command was the final flag for the room.

## Key Commands

* `ssh USERNAME@MACHINE_IP` - Connect to a remote machine using SSH
* `whoami` - Display the current user
* `ls` - List files and directories
* `cat FILENAME` - Display the contents of a file
* `history` - Display previously executed commands
* `su - root` - Switch to the root account
* `cd /root` - Navigate to the root user's home directory

## Conclusion

This room demonstrated how weak passwords, poor password practices, and careless handling of credentials can compromise an operating system.

The practical attack showed how an attacker could:

* Discover a weak user password
* Log in through SSH
* Inspect command history
* Recover a password accidentally entered into the terminal
* Escalate privileges to root
* Access files belonging to the root account

The main lesson is that strong authentication, proper permissions, and careful handling of credentials are essential for operating system security.
