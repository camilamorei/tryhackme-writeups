# Linux CLI Basics

## Introduction

This room introduces the basics of the Linux Command-Line Interface (CLI). The goal is to become comfortable navigating the Linux filesystem, finding files, reading their contents, and gathering basic system information.

These commands are fundamental for cybersecurity because many security tools and administrative tasks are performed through the terminal.

## Task 1 - Introduction

The first task introduced the Linux terminal and the Command-Line Interface (CLI).

CLI stands for:

```text
Command-Line Interface
```

The terminal provides a text-based way to interact with a Linux system by entering commands.

## Task 2 - Navigation Mission

The second task focused on navigating the Linux filesystem and finding files.

### Commands learned

`pwd` displays the current working directory:

```bash
pwd
```

`ls` lists files and directories:

```bash
ls
```

`ls -l` displays files with additional information such as permissions, ownership, size, and timestamps:

```bash
ls -l
```

`ls -al` also displays hidden files:

```bash
ls -al
```

`cd` is used to change directories:

```bash
cd Documents
```

To move back one directory:

```bash
cd ..
```

The `find` command can be used to locate files:

```bash
find ~ -name mission_brief.txt
```

After finding the file, `cat` can be used to read its contents:

```bash
cat mission_brief.txt
```

## Task 3 - Investigating the System

The third task focused on collecting basic information about the Linux system.

### Check the current user

The `whoami` command shows the username of the current user:

```bash
whoami
```

Example output:

```text
ubuntu
```

### Check kernel information

The `uname -a` command displays detailed information about the Linux kernel and system architecture:

```bash
uname -a
```

### Check disk usage

The `df -h` command displays disk usage in a human-readable format:

```bash
df -h
```

The `-h` option makes sizes easier to read, using units such as GB and MB.

The available disk space reported during the room was:

```text
58G
```

### Check the Linux distribution

Linux distribution information can be found in `/etc/os-release`.

```bash
cd /etc
cat os-release
```

The lab machine was running:

```text
Ubuntu 24.04.1 LTS
```

### Find the final report

The final challenge required finding `day1_report.txt` somewhere in the home directory.

The file can be located with:

```bash
find ~ -name day1_report.txt
```

After finding the file, its contents can be displayed with:

```bash
cat day1_report.txt
```

## Key Commands

* `pwd` - Display the current directory
* `ls` - List files and directories
* `ls -l` - List files with detailed information
* `ls -al` - List files including hidden files
* `cd` - Change directory
* `cd ..` - Move to the parent directory
* `find` - Search for files and directories
* `cat` - Display file contents
* `whoami` - Display the current username
* `uname -a` - Display system and kernel information
* `df -h` - Display disk usage in human-readable format

## Conclusion

This room covered the basic Linux CLI skills needed to work with a Linux system.

The main skills practiced were:

* Navigating the filesystem
* Listing files and directories
* Finding files
* Reading file contents
* Checking the current user
* Gathering kernel information
* Checking available disk space
* Identifying the Linux distribution

These commands are simple, but they are essential foundations for system administration, incident investigation, penetration testing, and other cybersecurity tasks.
