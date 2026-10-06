# Computer Types - TryHackMe

## Overview

* **Platform:** TryHackMe
* **Path:** Pre Security
* **Module:** Computer Fundamentals
* **Room:** Computer Types
* **Difficulty:** Easy
* **Goal:** Learn about different types of computers and understand what each type is designed for.

---

## Task 1 - Introduction

This room introduces the idea that computers are not limited to desktops and laptops.

Computers can be found in many everyday devices, including:

* Smartphones
* Tablets
* Servers
* IoT devices
* Embedded systems
* Smart appliances
* Sensors

One example from the room is a smart refrigerator connected to the Internet. It contains an embedded computer capable of communicating over a network.

### Key Concepts

**IoT (Internet of Things)**
Devices connected to a network that can send data or receive commands.

**Embedded Computer**
A computer integrated into another device to perform a specific function.

---

## Task 2 - Computers You Sit In Front Of

Different computers are designed for different purposes.

| Type        | Screen & Keyboard | Main Purpose                                        |
| ----------- | ----------------- | --------------------------------------------------- |
| Laptop      | Yes               | Portable everyday computing                         |
| Desktop     | Yes               | Sustained performance in a fixed location           |
| Workstation | Yes               | Precision and reliability for professional tasks    |
| Server      | Usually no        | Providing services to multiple users over a network |

### Laptop

A laptop is designed primarily for portability.

It uses compact components and a battery, making it suitable for:

* Web browsing
* Email
* Documents
* Studying
* General-purpose computing

### Desktop

A desktop is designed to remain in a fixed location.

Compared to laptops, desktops generally have more room for:

* Cooling
* Larger components
* Hardware expansion

This makes them suitable for sustained workloads.

### Workstation

A workstation is similar to a desktop but is designed for professional workloads that require precision and reliability.

Workstations can use specialized hardware for tasks such as:

* Simulations
* 3D modeling
* Engineering
* Complex calculations
* Professional workloads

### Server

A server provides services to other computers over a network.

Servers commonly operate without a dedicated monitor or keyboard and can handle requests from multiple users simultaneously.

---

## Task 2 - Answers

### Which type of computer generally operates without a dedicated screen and keyboard?

**Server**

### What type of computer with specialized components would someone buy to perform precision work?

**Workstation**

---

## Task 3 - Hidden Computers

The second part of the room introduces computers that we may interact with indirectly without realizing they are computers.

### Smartphone

A smartphone is a pocket-sized computer optimized for:

* Portability
* Battery life
* Connectivity
* Applications

Examples:

* iPhone
* Android smartphones

### Tablet

A tablet is a computer primarily designed for interaction through a touchscreen.

Examples:

* iPad
* Drawing tablets

### IoT Device

An IoT device is a network-connected device that usually has a specific purpose.

Examples:

* Smart thermostat
* Smart doorbell
* Fitness tracker

### Embedded Computer

An embedded computer is integrated into another device to control a specific function.

Examples:

* Coffee machine controller
* Automatic door sensor
* Smart light dimmer controller

---

## IoT vs Embedded Systems

IoT devices and embedded computers can both be small and designed for a specific purpose, but there is an important difference.

### IoT

An IoT device has network connectivity.

It can:

* Send data
* Receive commands
* Communicate with other devices or services

### Embedded

An embedded computer is integrated into another device and performs a specific function.

It does not necessarily need network connectivity.

### Example

An automatic door can contain a small computer that detects movement and sends a signal to the motor to open the door.

This is an example of **embedded computing**.

---

## Task 3 - Answers

### What is the most popular pocket-sized computer today?

**Smartphone**

### What type of computer would you expect to find inside a coffee machine?

**Embedded Computer**

---

## Key Takeaways

This room demonstrates that a computer does not necessarily look like a traditional PC.

The main types covered were:

```text
Laptop
Desktop
Workstation
Server
Smartphone
Tablet
IoT Device
Embedded Computer
```

The distinction between IoT and embedded systems is particularly important:

```text
IoT Device
└── Connected to a network
    ├── Sends data
    └── Receives commands

Embedded Computer
└── Integrated into another device
    └── Performs a specific function
        └── May work without network connectivity
```

Understanding these different types of computers is useful in cybersecurity because each type can have different hardware, operating systems, services, interfaces, and attack surfaces.
