# Client-Server Basics - TryHackMe

## Overview

* Platform: TryHackMe
* Path: Pre Security
* Module: Computer Fundamentals
* Room: Client-Server Basics
* Goal: Understand the fundamentals of the client-server model and how computers communicate over networks.

---

## Task 1 - Introduction

The client-server model describes how computers communicate to provide and consume services.

A client requests a service, while a server provides that service.

The room introduces several important concepts:

* Client
* Server
* Network
* Protocol
* Port
* DNS
* HTTP/HTTPS

---

## Task 2 - Pizza Delivery Analogy

The room uses a pizza delivery analogy to explain the client-server model.

Alice wants a pizza and gives her order to Bob. Bob takes the order to Luigi's Pizza, where the request is processed and a response is returned.

This can be compared to computer communication:

```text
Client
   │
   │ Request
   ▼
Server
   │
   │ Response
   ▼
Client
```

### Client

The client is the system that initiates a request.

For example, when visiting a website, the web browser acts as the client.

### Server

The server is the system that receives requests and provides services or resources.

For example, a web server can provide web pages to clients.

### Request and Response

Communication generally follows a request-response model:

```text
Client ───── Request ─────> Server
Client <──── Response ───── Server
```

If a request is invalid or the requested resource is unavailable, the server can return an error response.

---

## Protocol

A protocol defines the rules that systems use to communicate.

A protocol can define:

* Which commands are supported
* How requests are structured
* What syntax is used
* What response should be returned
* How invalid requests should be handled

Protocols allow different systems to understand each other.

---

## Ports

A port is used to identify a specific service running on a system.

A single server can run multiple services, with each service using a different port.

For example:

```text
Server
├── Port 22  → SSH
├── Port 80  → HTTP
└── Port 443 → HTTPS
```

The client must connect to the appropriate port to access a specific service.

### Answer

What do we use to identify a specific service on a server?

```text
Port
```

---

## DNS

DNS (Domain Name System) translates human-readable domain names into IP addresses.

For example:

```text
example.com
     │
     │ DNS
     ▼
IP address
```

This is similar to using a GPS to find the location of a destination from its name.

### Server Address

The address of a server is called an:

Internet Protocol address

or IP address.

---

## Task 3 - Web Communication in Practice

The room introduces HTTP(S) and demonstrates how a browser communicates with a web server.

### HTTP

HTTP (Hypertext Transfer Protocol) is a stateless client-server protocol used by the World Wide Web.

HTTP is described as stateless because each request is processed independently.

Modern web applications can introduce state at the application level using mechanisms such as:

* Cookies
* Session identifiers
* Tokens

These mechanisms allow applications to maintain information about a user's session between requests.

---

## HTTP Methods

The room introduces the following HTTP methods:

```text
GET
POST
PUT
DELETE
PATCH
HEAD
OPTIONS
CONNECT
TRACE
```

The room focuses on the GET method.

### GET

The GET method is used to retrieve a resource from a web server.

Example:

```text
GET https://tryhackme.com/index.php
```

When a user enters a URL into a browser, the browser constructs an HTTP request and sends it to the web server.

The server then sends a response.

---

## HTTP Request and Response

A typical interaction looks like:

```text
Browser
   │
   │ HTTP GET request
   ▼
Web Server
   │
   │ HTTP response
   ▼
Browser
```

The response contains:

* Response headers - metadata about the response
* Response body - the requested content

---

## Important HTTP Request Fields

When inspecting a request in browser developer tools, several important fields can be observed.

### Scheme

The scheme indicates which protocol is being used.

Examples:

```text
http
https
```

### Host

The host identifies the name of the server being requested.

Example:

```text
www.iamlearning.thm
```

### Filename / Path

The filename or path identifies the requested resource.

Example:

```text
/contact
```

### Address

The address shows the IP address where the website is hosted.

For example:

```text
127.0.0.1
```

This address represents the local machine.

### Status

The status indicates the result of the request.

For example:

```text
200 OK
```

means that the request was successful.

---

## URL Structure

A URL can be broken down into different components.

Example:

```text
https://www.iamlearning.thm/contact
```

```text
https://        www.iamlearning.thm        /contact
   │                    │                     │
 scheme                host                  path
```

### Answers

What would be the host in the following URL?

```text
www.iamlearning.thm
```

What would be the scheme in the following URL?

```text
https
```

---

## Key Takeaways

The client-server model is fundamental to understanding how services work across networks.

The main concepts covered in this room were:

```text
Client
Server
Network
Protocol
Port
DNS
IP Address
HTTP
HTTPS
GET
Request
Response
Host
Scheme
Status Code
```

A simplified web communication flow is:

```text
User
 │
 ▼
Browser (Client)
 │
 │ HTTP/HTTPS Request
 ▼
Server
 │
 │ Response
 ▼
Browser
```

Understanding these concepts is important for cybersecurity because network services are built around communication between clients and servers. Ports, protocols, IP addresses, HTTP requests, and responses are all fundamental concepts used when analyzing and securing networked systems.
