# Windows CLI Basics

## Introduction

This room introduces the basics of the Windows Command Prompt (CMD). The goal is to become comfortable navigating the Windows filesystem, finding files, reading their contents, and gathering basic system information.

These skills are useful in cybersecurity because Windows systems are widely used in organizations and are frequently involved in security investigations and troubleshooting.

## Task 1 - Introduction

The first task introduced the Windows Command Prompt.

The Command Prompt is a text-based interface that allows users to interact with Windows by entering commands instead of using the graphical interface.

The room also explained why the command line is useful for IT and cybersecurity work:

* It is faster than navigating through graphical interfaces
* It provides more control over the system
* Many administrative and security tools can be used from the command line

## Task 2 - Navigating Files and Finding Your First File

The second task focused on navigating the Windows filesystem and finding a specific file.

### Check the current directory

The `cd` command can be used without arguments to display the current directory:

```cmd
cd
```

It can also be used to change directories:

```cmd
cd Documents
```

To move between directories, the same command can be used with the desired path.

### List files and directories

The `dir` command lists the contents of the current directory:

```cmd
dir
```

To display hidden files and directories as well, use:

```cmd
dir /a
```

### Find a file

The `dir` command can also search through subdirectories.

For example, to find `task_brief.txt`:

```cmd
dir /s task_brief.txt
```

The `/s` option searches the current directory and all of its subdirectories.

### Read a file

The `type` command displays the contents of a text file:

```cmd
type task_brief.txt
```

This allows files to be read directly from the Command Prompt without opening them through a graphical text editor.

## Task 3 - Gathering System Information

The third task focused on collecting basic information about the Windows system.

### Check the current user

The `whoami` command displays the account currently logged in:

```cmd
whoami
```

### Check the computer name

The `hostname` command displays the name of the Windows computer:

```cmd
hostname
```

### Check Windows system information

The `systeminfo` command displays detailed information about the operating system and hardware:

```cmd
systeminfo
```

Important information includes:

* OS Name
* OS Version
* System Type
* Computer Name
* System information

The Windows version reported during the room was:

```text
10.0.17763 N/A Build 17763
```

### Check network information

The `ipconfig` command displays the network configuration of the Windows system:

```cmd
ipconfig
```

Important information includes:

* IPv4 Address
* Default Gateway
* Network adapter information

## Key Commands

* `cd` - Display or change the current directory
* `dir` - List files and directories
* `dir /a` - List files including hidden items
* `dir /s` - Search through subdirectories
* `type` - Display the contents of a text file
* `whoami` - Display the current user
* `hostname` - Display the computer name
* `systeminfo` - Display detailed Windows system information
* `ipconfig` - Display network configuration

## Conclusion

This room covered the basic Windows Command Prompt skills needed to work with a Windows system.

The main skills practiced were:

* Navigating the Windows filesystem
* Listing files and directories
* Finding files
* Viewing hidden files
* Reading files from the command line
* Identifying the current user
* Identifying the computer name
* Gathering Windows system information
* Checking basic network configuration

These commands provide a solid foundation for working with Windows systems and are useful for system administration, troubleshooting, and cybersecurity investigations.
