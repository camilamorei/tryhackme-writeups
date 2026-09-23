# TryHackMe — Linux Fundamentals Part 1

## Overview

This room introduces the fundamentals of using Linux through the command line.

The room covers basic Linux commands, navigating the filesystem, searching for files and text, and combining commands using operators and redirectors.

## Where is Linux used?

Linux is widely used in different environments, including:

* Web servers
* Car entertainment and control systems
* Point of Sale (PoS) systems
* Critical infrastructure
* Phones and other small computing devices
* Other computing systems

## Who are you on this machine?

The `whoami` command is used to determine the current user on a Linux system.

```bash
whoami
```

The `echo` command is used to output text.

```bash
echo "TryHackMe"
```

### Commands

| Command  | Description            |
| -------- | ---------------------- |
| `whoami` | Shows the current user |
| `echo`   | Outputs text           |

## Navigating the filesystem

Several basic commands can be used to navigate and inspect files and directories.

| Command | Description                            |
| ------- | -------------------------------------- |
| `ls`    | Lists files and directories            |
| `cd`    | Changes the current directory          |
| `cat`   | Displays the contents of a file        |
| `pwd`   | Displays the current working directory |

Example:

```bash
ls
pwd
cd folder1
cat passwords.txt
```

During the practical, `folder1` contained the files:

```text
access.log
passwords.txt
```

## Searching for files and text

Linux provides commands that make searching through files much easier.

### find

The `find` command can search for files by name.

```bash
find -name passwords.txt
```

### grep

The `grep` command searches for specific text inside files.

```bash
grep "THM" access.log
```

During the practical, the flag found in `access.log` was:

```text
THM{ACCESS}
```

## Combining commands and redirecting output

Linux provides operators that allow commands to be combined and their output to be redirected.

### &

Runs a command in the background without waiting for it to finish.

```bash
command &
```

### &&

Runs the second command only after the first command has finished successfully.

```bash
command1 && command2
```

### >

Redirects command output to a file and overwrites the existing contents.

```bash
echo "TryHackMe" > thm
```

### >>

Redirects command output to a file without overwriting its existing contents.

```bash
echo "TryHackMe" >> thm
```

The `cat` command can then be used to view the contents:

```bash
cat thm
```

## Answers

| Question                                            | Answer        |
| --------------------------------------------------- | ------------- |
| Command used to identify the current user           | `whoami`      |
| Command used to output text                         | `echo`        |
| Folder containing the file                          | `folder1`     |
| Flag found in `access.log`                          | `THM{ACCESS}` |
| Operator that waits for the first command to finish | `&&`          |
| Redirector that does not overwrite existing content | `>>`          |

## What I Learned

This room introduced the fundamentals of working with Linux from the command line.

Key concepts covered:

* Identifying the current user with `whoami`
* Displaying text with `echo`
* Navigating directories with `cd`
* Listing files with `ls`
* Checking the current directory with `pwd`
* Reading files with `cat`
* Searching for files with `find`
* Searching inside files with `grep`
* Combining commands with `&&`
* Running commands in the background with `&`
* Redirecting output with `>` and `>>`

These commands are fundamental for working with Linux systems and are especially useful in cybersecurity.
