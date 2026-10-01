# Operating Systems Introduction

## Overview

An operating system (OS) is the core software that manages hardware, applications, users, and system resources.

It acts as an intermediary between the user, applications, and physical hardware, allowing the computer to operate as a unified system.

## Kernel Space and User Space

Modern operating systems separate system privileges into different areas.

### Kernel Space

Kernel space is the highly privileged area where the OS kernel runs.

The kernel has direct and unrestricted access to system hardware and resources such as:

* CPU
* Memory
* Storage
* Hardware devices

### User Space

User space is where regular applications run.

Applications have limited permissions and cannot directly access hardware. When they need system resources, they make system calls that are handled by the kernel.

This separation improves system stability and security by preventing applications from directly interfering with critical system resources.

## Operating System Responsibilities

The main responsibilities of an operating system include:

* Process Management: Creates, schedules, prioritizes, and terminates processes.
* Memory Management: Allocates and protects RAM between processes and manages virtual memory.
* File System Management: Organizes files and directories and manages permissions and metadata.
* User Management: Handles user accounts, authentication, and permissions.
* Device Management: Manages hardware devices through drivers and provides applications with interfaces to use them.

## Operating System Security

Operating systems provide several fundamental security mechanisms:

* Authentication: Verifies user identities through passwords and other methods.
* Permissions: Controls what users and applications can access.
* Isolation: Separates processes and protects system resources.
* System Protection: Prevents unauthorized changes to critical files and settings.

## OS Interfaces

There are two main ways to interact with an operating system:

### Graphical User Interface (GUI)

A GUI provides visual elements such as windows, icons, menus, and folders.

It makes the operating system easier to use for common tasks.

### Command-Line Interface (CLI)

A CLI uses text-based commands to interact with the operating system.

It provides precise control and is especially useful for system administration, automation, and cybersecurity.

## Operating System Types

The main operating system categories are:

* Desktop: Personal computers, gaming, and daily work.
* Server: Web hosting, databases, cloud services, and back-end systems.
* Mobile: Smartphones and tablets.
* Embedded: IoT devices, appliances, cars, routers, and smart TVs.
* Virtual/Cloud: Virtual machines, containers, and cloud instances.

## Common Operating Systems

### Desktop

* Windows
* macOS
* Linux

### Server

* Windows Server
* Linux distributions
* Unix systems

### Mobile

* Android
* iOS

### Embedded and IoT

* Embedded Linux
* FreeRTOS
* VxWorks
* QNX

### Virtual and Cloud

* Ubuntu LTS
* Amazon Linux
* Rocky Linux
* Alpine Linux
* Bottlerocket

## System Investigation

During the practical investigation, I used the System Monitor and file system of the provided Ubuntu MATE machine.

The investigation included:

* Checking the system's OS information.
* Inspecting the available memory.
* Examining the file system information for `/dev/root`.
* Investigating the user directories in the Home directory.
* Exploring Alex's Documents directory.

The flag found in `note.txt` is intentionally not included in this writeup.

## Key Takeaways

* The operating system manages hardware, applications, users, and system resources.
* Kernel space has unrestricted access to hardware.
* User space provides a restricted environment for normal applications.
* Process, memory, file system, user, and device management are core OS responsibilities.
* Operating systems provide important security mechanisms such as authentication, permissions, isolation, and system protection.
* GUI and CLI are two primary ways to interact with an operating system.
* Different operating systems are designed for different environments and requirements.

## Further Learning

The next rooms in the Operating System module cover:

* Windows Basics
* Linux CLI Basics
* Windows CLI Basics
