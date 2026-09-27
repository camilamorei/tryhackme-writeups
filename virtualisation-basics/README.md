# Virtualisation Basics - TryHackMe

## Overview

* Platform: TryHackMe
* Path: Pre Security
* Module: Computer Fundamentals
* Room: Virtualisation Basics
* Goal: Understand virtualization, hypervisors, virtual machines, containers, and how virtualization improves hardware efficiency and isolation.

## Task 1 - Introduction

Virtualization allows a single physical computer to act as multiple independent virtual computers.

Before virtualization, the common approach was:

```text
1 Physical Server
        |
   1 Application
```

This approach could lead to high costs, low hardware utilization, slow deployment, and difficulties scaling applications.

Virtualization solves these problems by allowing multiple virtual machines to share the same physical hardware.

## Task 2 - Virtualisation Overview

Before virtualization, companies often followed the model:

```text
1 Server = 1 Application
```

This resulted in:

* High hardware and infrastructure costs
* Low CPU, memory, and storage utilization
* Slow server deployment
* Difficult scaling

A hypervisor was introduced to safely divide a physical server into multiple virtual machines.

### Building Analogy

The virtualization model can be compared to an apartment building:

```text
Physical Server = Building
Virtual Machines = Apartments
Applications / Operating Systems = Tenants
Hypervisor = Building Manager
```

Each virtual machine operates independently while sharing the underlying physical hardware.

### Key Concepts

* Client applications can share physical hardware.
* A hypervisor manages the resources allocated to virtual machines.
* Each VM has its own operating system, applications, and configuration.

## Task 3 - Virtualisation Components

### Hypervisor

A hypervisor is the software responsible for creating and managing virtual machines.

It can:

* Divide physical hardware between multiple VMs
* Allocate CPU, memory, and storage
* Isolate virtual machines
* Start, stop, pause, clone, and delete VMs

### Type 1 Hypervisor

A Type 1 hypervisor runs directly on physical hardware.

```text
Physical Hardware
       |
   Hypervisor
       |
   Virtual Machines
```

It is commonly used for:

* Production servers
* Database servers
* Data centers

### Type 2 Hypervisor

A Type 2 hypervisor runs on top of an existing operating system.

```text
Physical Hardware
       |
   Host Operating System
       |
   Type 2 Hypervisor
       |
   Virtual Machines
```

It is commonly used for:

* Learning
* Testing
* Software development
* Running Kali Linux in a VM

Examples include VirtualBox and VMware Workstation.

### Virtual Machines

A virtual machine is a computer created and managed by a hypervisor.

A VM can have:

* Virtual CPU
* Virtual memory
* Virtual storage
* Virtual network
* Its own operating system

VMs provide strong isolation and flexibility.

### Containers

Containers are lightweight isolated environments designed to run applications and their dependencies.

Unlike a VM, a container does not require a complete separate operating system. Containers share the host operating system kernel.

```text
Host Operating System
        |
      Kernel
     /      \
Container  Container
   App        App
```

Because they share the host kernel, containers start quickly and require fewer resources than full virtual machines.

### Docker

Docker is a platform used to create, deploy, and run containerized applications.

Containers are useful for:

* Development
* Testing
* Application deployment
* Scalable services

## Task 4 - Managing Virtual Machines

The Virtualization Manager was used to manage the virtual environment.

The tasks included:

* Restarting the `Mail-SERVER` VM after it entered an error state
* Creating a new VM called `Marketing-VM`
* Assigning hardware resources to the new VM
* Checking physical host resource usage

### Marketing-VM Configuration

```text
Name: Marketing-VM
CPU: 4 cores
Memory: 8 GB
Disk: 100 GB
```

### Lab Machine Answers

Longest-running VM:

```text
Monitoring-SYS
```

VM using the most memory:

```text
DB-Cluster-01
```

Number of running VMs after restarting `Mail-SERVER`:

```text
7
```

Physical host hosting the most VMs:

```text
HV-PROD-02
```

## Task 5 - Conclusion

Virtualization is an important foundation of modern IT because it improves hardware utilization while providing isolation between environments.

### Key Takeaways

* Virtualization allows one physical computer to run multiple virtual computers.
* A hypervisor creates and manages virtual machines.
* Type 1 hypervisors run directly on physical hardware.
* Type 2 hypervisors run on top of an existing operating system.
* VMs provide complete virtualized environments.
* Containers are lighter than VMs and share the host kernel.
* Docker is commonly used to create and manage containers.
* Virtualization improves cost efficiency, resource utilization, scalability, flexibility, portability, and deployment speed.
* Virtualization is also useful for cybersecurity labs and safely testing applications in isolated environments.

## Cybersecurity Relevance

Virtualization is highly relevant to cybersecurity because it allows security professionals and students to create isolated environments for testing and learning.

For example:

```text
Host Machine
     |
 Hypervisor
     |
     +---- Kali Linux VM
     |
     +---- Windows VM
     |
     +---- Vulnerable Lab VM
```

This makes it possible to build cybersecurity labs without requiring a separate physical computer for every operating system or environment.

Virtualization is also an important foundation for cloud computing, containers, and modern infrastructure.
