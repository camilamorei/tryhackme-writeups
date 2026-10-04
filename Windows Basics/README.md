# Windows Basics

TryHackMe room: Windows Basics

## Overview

This room introduces the Windows operating system through a hands-on Windows Server 2019 environment.

The lab simulates the first day of a new employee at TryHatMe. The main goal is to become familiar with the Windows graphical interface, system settings, file management, applications, and basic security tools.

## Learning Objectives

* Navigate the Windows graphical interface
* Understand the Desktop, Taskbar, and Start Menu
* Use File Explorer to browse and manage files
* Understand Windows file paths
* Explore system information and settings
* Install and manage applications
* Use Task Manager to monitor the system
* Use Windows Security and perform a custom scan
* Understand the role of Windows Defender Firewall

## Environment

* Operating System: Windows Server 2019 Datacenter
* User account: Administrator
* Lab environment: TryHatMe workstation

## Windows Desktop

The Windows Desktop is the main workspace of the operating system.

Important components include:

* Desktop icons
* Start Menu
* Search
* Task View
* Pinned applications and folders
* Network and audio settings
* Date and time
* Notifications
* Taskbar

The Start Menu provides access to applications, settings, files, folders, and power options.

## File Explorer

File Explorer is used to browse, organize, and manage files and folders.

Windows uses a hierarchical folder structure where folders can contain other folders and files.

Example path used in the lab:

`C:\Users\Administrator\Desktop\TryHatMe Onboarding`

File Explorer can also be used to search for files and navigate through directories.

## System Information

The About your PC section provides information about the computer, including:

* Device specifications
* Installed RAM
* Device name
* Windows edition and version
* Other system information

## Application Management

Windows applications can be installed and updated in different ways.

Common methods include:

* Microsoft Store
* Downloading an installer from a trusted vendor
* Built-in application update mechanisms
* Manual installers such as `.exe` and `.msi` files

Applications can be removed through Settings, Control Panel, the Microsoft Store, or an application's built-in uninstaller.

## Settings and Control Panel

Windows provides two main configuration interfaces.

### Windows Settings

The Settings application is the modern interface for configuring:

* System settings
* Devices
* Personalization
* User accounts
* Applications
* Network settings
* Accessibility
* Security options

### Control Panel

Control Panel is the legacy Windows configuration interface. It is still used for some administrative and system configuration tasks.

## Task Manager

Task Manager allows users to monitor the system in real time.

Important sections include:

* Processes
* Performance
* Users
* Details
* Services

The Users tab can be used to see accounts currently logged into the system.

## Windows Security

Windows Security provides access to several built-in security features.

Important sections include:

* Virus & threat protection
* Firewall & network protection
* App & browser control
* Device security

During the lab, a custom scan was performed against the TryHatMe Onboarding folder.

The scan detected the EICAR test file:

`Virus:DOS/EICAR_Test_File`

The affected item was investigated through the Windows Security interface.

## Windows Defender Firewall

Windows Defender Firewall helps protect the system from unauthorized network traffic.

Windows Firewall uses different network profiles:

* Domain
* Private
* Public

Advanced Firewall settings allow administrators to inspect inbound and outbound rules and create or modify firewall rules.

## Key Takeaways

This room provided practical experience with the Windows graphical interface and basic system administration tasks.

I learned how to:

* Navigate Windows
* Manage files and folders
* Check system information
* Install and remove applications
* Use Windows Settings and Control Panel
* Monitor processes with Task Manager
* Use Windows Security
* Perform a custom malware scan
* Understand the basic purpose of Windows Defender Firewall

## Conclusion

Windows Basics provided a practical introduction to using and managing a Windows environment. The knowledge gained from this room provides a foundation for working with the Windows command line and exploring more advanced operating system concepts.

## Next Steps

The next rooms of the module are:

* Linux CLI Basics
* Windows CLI Basics
