# OSI Model

TryHackMe room covering the seven layers of the OSI (Open Systems Interconnection) model and how data is transmitted across a network.

## Topics Covered

* OSI Model
* Physical Layer
* Data Link Layer
* Network Layer
* Transport Layer
* Session Layer
* Presentation Layer
* Application Layer
* TCP and UDP
* IP and MAC addresses
* Routing
* Encapsulation
* Packets and Frames

## OSI Model Layers

| Layer | Name         | Main Function                                               |
| ----- | ------------ | ----------------------------------------------------------- |
| 7     | Application  | Provides network services and user interaction              |
| 6     | Presentation | Translates, formats, encrypts and decrypts data             |
| 5     | Session      | Establishes and manages communication sessions              |
| 4     | Transport    | Provides end-to-end data transmission using TCP or UDP      |
| 3     | Network      | Handles IP addressing and routing                           |
| 2     | Data Link    | Handles MAC addressing and physical transmission formatting |
| 1     | Physical     | Transmits data as electrical or physical signals            |

## Key Concepts

### Layer 1 — Physical

The Physical layer deals with the physical components used for networking.

Data is transmitted using binary values (`0` and `1`) through physical media such as Ethernet cables.

### Layer 2 — Data Link

The Data Link layer handles physical addressing using MAC addresses.

Network Interface Cards (NICs) contain MAC addresses that identify devices on a network.

### Layer 3 — Network

The Network layer is responsible for IP addressing and routing packets between networks.

Routing protocols covered in the room include:

* OSPF — Open Shortest Path First
* RIP — Routing Information Protocol

### Layer 4 — Transport

The Transport layer handles communication between devices using protocols such as TCP and UDP.

**TCP** provides reliable communication, error checking and ordered delivery.

**UDP** is faster but does not guarantee that packets will arrive or arrive in the correct order.

### Layer 5 — Session

The Session layer establishes and maintains communication sessions between devices.

It can also manage checkpoints and terminate inactive or lost sessions.

### Layer 6 — Presentation

The Presentation layer acts as a translator between different data formats.

It is also responsible for functions such as encryption and decryption.

### Layer 7 — Application

The Application layer contains protocols and services that applications use to communicate over a network.

Examples include DNS and applications such as web browsers and email clients.

## Important Protocols

| Protocol | Purpose                                       |
| -------- | --------------------------------------------- |
| TCP      | Reliable and ordered data transmission        |
| UDP      | Fast transmission without guaranteed delivery |
| OSPF     | Routing protocol                              |
| RIP      | Routing protocol                              |
| DNS      | Translates domain names into IP addresses     |

## Practical

The room includes an interactive OSI Game where the objective is to escape the dungeon by progressing through the OSI layers in the correct order.

The correct order is:

`7 → 6 → 5 → 4 → 3 → 2 → 1`

## What I Learned

This room helped me understand how network communication can be divided into different layers, with each layer performing a specific function.

Understanding the OSI model is important for troubleshooting networks, analyzing traffic and understanding where protocols and network technologies operate.
