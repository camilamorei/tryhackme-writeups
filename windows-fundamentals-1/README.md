# TryHackMe - Windows Fundamentals 1

## Overview

This room provides an introduction to the Windows operating system, covering Windows editions, the graphical user interface (GUI), NTFS, user accounts and permissions, User Account Control (UAC), system settings, Control Panel, and Task Manager.

The room also includes hands-on interaction with a Windows virtual machine.

---

## Task 1 - Windows Editions

Windows has several editions designed for different use cases. Windows 11 is available in Home and Pro editions, while Windows Server has separate editions for server environments.

One important difference between Windows editions is the availability of certain security features.

### Question

What encryption can you enable on Pro that you can't enable in Home?

Answer: `BitLocker`

### What I learned

BitLocker is Microsoft's full-volume encryption feature. It can be used to protect data stored on a drive if the device is lost or stolen.

---

## Task 2 - The Desktop (GUI)

The Windows graphical user interface contains several components, including:

* Desktop
* Start Menu
* Search
* Task View
* Taskbar
* Toolbars
* Notification Area

### Questions

Which selection will hide/disable the Search box?

Answer: `Search → Hidden`

Which selection will hide/disable the Task View button?

Answer: Disable/uncheck `Show Task View button`

Besides Clock and Network, what other icon is visible in the Notification Area?

Answer: `Volume`

### What I learned

The Windows desktop provides quick access to applications, files, system settings, and currently running programs. The Taskbar and Notification Area can also be customized to control which system features are visible.

---

## Task 3 - Introduction to Windows

This section introduced the Windows laboratory environment and the process of interacting with a Windows machine remotely.

The lab uses a Windows machine that can be accessed through the TryHackMe environment.

### What I learned

Remote Desktop Protocol (RDP) can be used to remotely access a Windows system with appropriate credentials.

For security reasons, lab credentials are not included in this public writeup.

---

## Task 4 - Windows File System

Modern Windows systems primarily use the New Technology File System (NTFS).

NTFS provides several features that are important for Windows systems, including:

* Support for files larger than 4 GB
* File and folder permissions
* File and folder compression
* Encryption through Encrypting File System (EFS)
* Journaling for improved filesystem reliability
* Alternate Data Streams (ADS)

### Question

What is the meaning of NTFS?

Answer: `New Technology File System`

### NTFS Permissions

NTFS supports permissions such as:

* Full Control
* Modify
* Read & Execute
* List Folder Contents
* Read
* Write

These permissions can be viewed through the Security tab in the properties of a file or folder.

### Alternate Data Streams

Alternate Data Streams (ADS) are a feature specific to NTFS that allows additional streams of data to be associated with a file.

From a cybersecurity perspective, ADS is important because it can potentially be abused to hide data. It also has legitimate uses, such as storing information associated with files downloaded from the Internet.

### What I learned

Understanding NTFS permissions and ADS is important when analyzing Windows systems from a cybersecurity perspective.

---

## Task 5 - Windows\System32

The Windows operating system is traditionally installed under:

```text
C:\Windows
```

However, the Windows directory can technically be located elsewhere.

Windows provides the `%windir%` environment variable to reference the Windows installation directory.

### Question

What is the system variable for the Windows folder?

Answer:

```text
%windir%
```

### System32

The System32 directory contains important Windows system files and utilities.

Because many critical components of Windows are stored there, modifying or deleting files from this directory can cause serious problems.

### What I learned

Environment variables provide a convenient way for applications and users to reference important system locations without hardcoding their paths.

---

## Task 6 - User Accounts, Profiles and Permissions

Windows local accounts can generally be classified as:

* Administrator
* Standard User

Administrators can perform system-level changes, while Standard Users have more restricted permissions.

When a user account is created, Windows creates a corresponding user profile, normally under:

```text
C:\Users\<username>
```

A user profile contains directories such as:

* Desktop
* Documents
* Downloads
* Music
* Pictures

### Local Users and Groups

The `lusrmgr.msc` utility can be used to manage local users and groups.

Users can belong to multiple groups and inherit permissions associated with those groups.

### Questions

What is the built-in account for guest access to the computer?

Answer:

```text
Guest
```

What is the description of the Guest account?

The description identifies it as the built-in account intended for guest access to the computer/domain.

> Lab-specific credentials and secrets were intentionally omitted from this writeup.

### What I learned

Windows permissions are strongly connected to users and groups. Understanding group membership is important when analyzing what actions a user is authorized to perform.

---

## Task 7 - User Account Control (UAC)

User Account Control (UAC) is a Windows security feature designed to prevent unauthorized operations from automatically running with elevated privileges.

Even when an administrator is logged in, applications do not automatically receive elevated privileges for every operation.

When an action requires elevation, Windows can display a UAC prompt asking for confirmation or administrator credentials.

### Question

What does UAC mean?

Answer:

```text
User Account Control
```

### What I learned

UAC helps reduce the impact of malware and other unauthorized actions by requiring elevation when an operation needs higher privileges.

The distinction between normal and elevated privileges is important when analyzing Windows security.

---

## Task 8 - Settings and Control Panel

Windows provides two major locations for configuring the operating system:

* Settings
* Control Panel

Settings is the newer interface, while Control Panel continues to provide access to many advanced and legacy configuration options.

The Programs and Features section of Control Panel can be used to view installed applications.

### Question

After changing Control Panel to Small icons, what is the last setting shown?

Answer:

```text
Windows Defender Firewall with Advanced Security
```

### What I learned

Some Windows configuration options are still managed through Control Panel even though Microsoft has moved many settings into the newer Settings application.

---

## Task 9 - Task Manager

Task Manager provides information about applications and processes currently running on the system.

It also provides information about resource usage, including:

* CPU
* Memory
* Disk
* Network
* GPU

Task Manager can be opened through the taskbar or using a keyboard shortcut.

### Question

What is the keyboard shortcut to open Task Manager?

Answer:

```text
Ctrl + Shift + Esc
```

### What I learned

Task Manager is useful for investigating running processes and system resource usage. From a cybersecurity perspective, it can also be a useful starting point when investigating suspicious processes or unusual resource consumption.

---

# Key Takeaways

This room introduced several Windows concepts that are relevant to cybersecurity:

* Windows editions provide different features and security capabilities.
* NTFS provides permissions, encryption, journaling, and other filesystem features.
* NTFS permissions control access to files and directories.
* Alternate Data Streams (ADS) can store additional data associated with files.
* Environment variables such as `%windir%` provide references to important system locations.
* Users and groups determine what actions an account can perform.
* UAC helps prevent unauthorized elevation of privileges.
* Control Panel and Settings provide different interfaces for configuring Windows.
* Task Manager allows users and analysts to inspect processes and resource usage.

## Skills Practiced

* Windows GUI navigation
* Windows user and group management
* NTFS concepts and permissions
* Environment variables
* Windows security concepts
* UAC
* Basic Windows system administration
* Task Manager and process awareness
* Remote access to Windows laboratory environments


Room: Windows Fundamentals 1

