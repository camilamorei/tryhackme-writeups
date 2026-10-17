# TryHackMe: Web Application Basics

## Room Information

- Platform: TryHackMe
- Room: Web Application Basics
- Category: Web Fundamentals
- Difficulty: Beginner
- Status: Completed

## Overview

This room introduces the fundamental components of web applications and explains how browsers communicate with web servers using HTTP. It covers URL structures, HTTP requests and responses, request methods, headers, status codes, and security headers.

## Learning Objectives

- Understand front-end and back-end web application components.
- Identify the different parts of a URL.
- Understand HTTP requests and responses.
- Learn common HTTP methods and status codes.
- Identify HTTP request and response headers.
- Understand security headers and their role in protecting web applications.
- Perform basic HTTP requests using the TryHackMe emulator.

## Task 1: Introduction

Completed the introduction to web applications.

## Task 2: Web Application Overview

1. Component responsible for hosting and delivering web application content: `Web Server`
2. Tool used to access and interact with web applications: `Web Browser`
3. Component that filters malicious incoming traffic: `WAF` (Web Application Firewall)

## Task 3: Uniform Resource Locator (URL)

1. Protocol that encrypts communication between a browser and server: `HTTPS`
2. Registering misspelled variations of popular domain names: `Typosquatting`
3. URL component used to pass search terms and form inputs: `Query String`

## Task 4: HTTP Messages

1. Message returned by a web server after processing a request: `HTTP Response`
2. Component that separates HTTP headers from the body: `Empty Line`

## Task 5: HTTP Request: Request Line and Methods

1. HTTP version that introduced persistent connections and chunked transfer encoding: `HTTP/1.1`
2. Method used to discover supported communication options for a resource: `OPTIONS`
3. Component identifying the requested resource after the domain name: `URL Path`

## Task 6: HTTP Request: Headers and Body

1. Header specifying the destination web server's domain name: `Host`
2. Default content type for URL encoded form submissions: `application/x-www-form-urlencoded`
3. Component containing information such as Host, User-Agent, and Content-Type: `Request Headers`

## Task 7: HTTP Response: Status Line and Status Codes

1. Response component containing the HTTP version, status code, and reason phrase: `Status Line`
2. Category indicating server-side errors: `Server Error Responses (500-599)`
3. Status code indicating that a resource could not be found: `404`

## Task 8: HTTP Response: Headers and Body

1. Header that can disclose web server software information: `Server`
2. Cookie flag restricting transmission to HTTPS connections: `Secure`
3. Cookie flag preventing access through JavaScript: `HttpOnly`

## Task 9: Security Headers

1. CSP property specifying permitted script sources: `script-src`
2. HSTS directive applying the policy to subdomains: `includeSubDomains`
3. X-Content-Type-Options directive preventing MIME type sniffing: `nosniff`

## Task 10: Practical Task: Making HTTP Requests

### 1. GET `/api/users`

- Method: `GET`
- Endpoint: `/api/users`
- Flag: `THM{YOU_HAVE_JUST_FOUND_THE_USER_LIST}`

### 2. POST `/api/user/2`

- Method: `POST`
- Endpoint: `/api/user/2`
- Objective: Update Bob's country from UK to US.
- Request body: `country=US`
- Content-Type: `application/x-www-form-urlencoded`
- Flag: `THM{YOU_HAVE_MODIFIED_THE_USER_DATA}`

### 3. DELETE `/api/user/1`

- Method: `DELETE`
- Endpoint: `/api/user/1`
- Objective: Delete user #1.
- Flag: `THM{YOU_HAVE_JUST_DELETED_A_USER}`

## Task 11: Conclusion

Completed the room and reviewed the fundamentals of web applications, HTTP communication, URL anatomy, and security headers.

## Key Takeaways

- HTML defines web page structure, CSS controls presentation, and JavaScript enables interactivity.
- Web servers process requests and deliver application content.
- HTTP methods define the intended action for a resource.
- HTTP status codes indicate the result of a request.
- Request and response headers provide metadata and processing instructions.
- Security headers help mitigate attacks such as Cross-Site Scripting (XSS), clickjacking, and MIME type sniffing.
- HTTP requests can be tested using methods such as GET, POST, and DELETE.

## Completion Status

Room completed successfully.
