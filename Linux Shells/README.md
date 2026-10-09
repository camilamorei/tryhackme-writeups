# Linux Shells

## Introduction

This room explores Linux shells, their features, and how they are used to interact with the operating system through the command-line interface (CLI). It also introduces shell scripting and demonstrates how scripts can automate repetitive tasks.

## Learning Objectives

* Understand how Linux shells work.
* Learn basic shell commands.
* Explore different types of Linux shells.
* Understand variables, loops, conditional statements, and comments.
* Create and execute Bash scripts.
* Use shell scripting to search files and retrieve information.

## Tasks Completed

### Task 1: Introduction to Linux Shells

Learned the difference between a graphical user interface (GUI) and a command-line interface (CLI), and understood how a shell acts as an intermediary between the user and the operating system.

### Task 2: How To Interact With a Shell?

Practiced basic Linux commands for navigating directories, listing files, reading file contents, and searching for specific text.

Commands covered:

* `pwd` — Displays the current working directory.
* `cd` — Changes the current directory.
* `ls` — Lists directory contents.
* `cat` — Displays file contents.
* `grep` — Searches for patterns in files.

### Task 3: Types of Linux Shells

Explored three common Linux shells:

* Bash (Bourne Again Shell)
* Fish (Friendly Interactive Shell)
* Zsh (Z Shell)

Learned about their differences in scripting, command completion, customization, syntax highlighting, and automatic spelling correction.

Also learned how to inspect the current shell using `echo $SHELL`, list available shells through `/etc/shells`, and review previously executed commands using `history`.

### Task 4: Shell Scripting and Components

Learned the fundamental components of Bash scripting, including:

* Shebang: `#!/bin/bash`
* Variables and user input using `read`
* Output using `echo`
* Loops for repetitive operations
* Conditional statements using `if`, `else`, and `fi`
* Comments for code documentation
* Script execution permissions using `chmod +x`

Created example scripts to collect user input, display numbers from 1 to 10, and verify whether a user is authorized to access a specific message.

### Task 5: The Locker Script

Analyzed a Bash script that authenticates a user using a username, company name, and PIN.

The script uses variables, a loop, and conditional statements to collect and validate the credentials.

Required credentials:

* Username: `John`
* Company name: `Tryhackme`
* PIN: `7385`

The script grants access only when all three values match the expected credentials.

### Task 6: Practical Exercise

Modified and executed a provided shell script to search for a specific keyword in `.log` files inside `/var/log`.

The exercise involved understanding script variables, correcting missing values, and searching system log files to retrieve the requested information.

Results:

* File containing the keyword: `/var/log/authentication.log`
* Cat's location: `under the table`

### Task 7: Conclusion

Completed the room and reviewed the main concepts of Linux shells and Bash scripting.

## Key Takeaways

This room provided practical experience with Linux command-line interaction and basic automation. Understanding shell commands and scripting is useful for cybersecurity tasks such as log analysis, system administration, incident investigation, and repetitive task automation.

These skills provide a foundation for further study in Linux administration, security operations, and incident response.

## Tools and Technologies

* Linux
* Bash
* Linux CLI
* Nano
* Linux system logs
* TryHackMe

## Conclusion

Completing this room strengthened my understanding of Linux shells and introduced me to the fundamentals of Bash scripting. I practiced using commands to navigate the filesystem, search for information, and automate simple tasks. These concepts are important foundations for my continued cybersecurity learning.
