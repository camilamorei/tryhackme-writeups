# HTTP In Detail

TryHackMe room focused on understanding HTTP and HTTPS, requests and responses, HTTP methods, status codes, headers, cookies, and making HTTP requests.

Room: https://tryhackme.com/room/httpindetail

## Task 1: What is HTTP(S)?

HTTP stands for:

`HyperText Transfer Protocol`

HTTPS stands for:

`HyperText Transfer Protocol Secure`

HTTPS is the secure version of HTTP. It encrypts data sent between the client and web server and helps verify that the client is communicating with the intended web server.

## Task 2: Requests And Responses

A URL is used to specify how and where a resource on the internet can be accessed.

A URL can contain:

| Component    | Description                                                 |
| ------------ | ----------------------------------------------------------- |
| Scheme       | Protocol used to access the resource, such as HTTP or HTTPS |
| User         | Username and password used for authentication               |
| Host         | Domain name or IP address of the server                     |
| Port         | Port used to connect to the server                          |
| Path         | Location of the requested resource                          |
| Query String | Additional parameters sent with the request                 |
| Fragment     | Reference to a specific location on a page                  |

Example URL:

`http://user:password@tryhackme.com:80/view-room?id=1#task3`

An HTTP request contains a method, path, HTTP version, and headers.

Example:

```http
GET / HTTP/1.1
Host: tryhackme.com
User-Agent: Mozilla/5.0 Firefox/87.0
Referer: https://tryhackme.com/
```

The response contains the HTTP version, status code, response headers, and the requested content.

Example:

```http
HTTP/1.1 200 OK

Server: nginx/1.15.8
Date: Fri, 09 Apr 2021 13:34:03 GMT
Content-Type: text/html
Content-Length: 98
```

HTTP protocol used in the example:

`HTTP/1.1`

Response header that tells the browser how much data to expect:

`Content-Length`

## Task 3: HTTP Methods

HTTP methods tell the web server what action the client wants to perform.

| Method | Purpose                              |
| ------ | ------------------------------------ |
| GET    | Retrieve information                 |
| POST   | Submit data or create a new resource |
| PUT    | Update information                   |
| DELETE | Delete information                   |

Create a new user account:

`POST`

Update an email address:

`PUT`

Remove an uploaded picture:

`DELETE`

View a news article:

`GET`

## Task 4: HTTP Status Codes

HTTP status codes are divided into five main ranges:

| Range   | Meaning                |
| ------- | ---------------------- |
| 100-199 | Informational Response |
| 200-299 | Success                |
| 300-399 | Redirection            |
| 400-499 | Client Errors          |
| 500-599 | Server Errors          |

Common status codes:

| Status Code | Meaning               |
| ----------- | --------------------- |
| 200         | OK                    |
| 201         | Created               |
| 301         | Moved Permanently     |
| 302         | Found                 |
| 400         | Bad Request           |
| 401         | Not Authorised        |
| 403         | Forbidden             |
| 404         | Page Not Found        |
| 405         | Method Not Allowed    |
| 500         | Internal Server Error |
| 503         | Service Unavailable   |

Creating a new user or blog post:

`201`

Accessing a page that does not exist:

`404`

When the web server cannot access its database and the application becomes unavailable:

`503`

Trying to edit a profile without logging in:

`401`

## Task 5: Headers

Headers contain additional information sent between the client and web server.

Common request headers include:

| Header          | Purpose                                    |
| --------------- | ------------------------------------------ |
| Host            | Specifies which website is being requested |
| User-Agent      | Identifies the browser and its version     |
| Content-Length  | Tells the server how much data to expect   |
| Accept-Encoding | Specifies supported compression methods    |
| Cookie          | Sends stored cookie data to the server     |

Common response headers include:

| Header           | Purpose                                       |
| ---------------- | --------------------------------------------- |
| Set-Cookie       | Tells the browser to store a cookie           |
| Cache-Control    | Controls how long content should be cached    |
| Content-Type     | Specifies the type of data being returned     |
| Content-Encoding | Specifies how the response data is compressed |

Header that tells the web server what browser is being used:

`User-Agent`

Header that tells the browser what type of data is being returned:

`Content-Type`

Header that tells the web server which website is being requested:

`Host`

## Task 6: Cookies

Cookies are small pieces of data stored on the user's computer.

The server can send a `Set-Cookie` header to tell the browser to store a cookie. The browser then sends the cookie back to the server with subsequent requests.

Cookies are commonly used for authentication, storing user preferences, and maintaining information about a user's session.

Header used to save cookies to the computer:

`Set-Cookie`

## Task 7: Making Requests

The final task involved using the HTTP request emulator to create different types of HTTP requests.

### GET /room

```http
GET /room
```

### GET /blog?id=1

```http
GET /blog?id=1
```

### DELETE /user/1

```http
DELETE /user/1
```

### PUT /user/2

The request used the `username` parameter with the value `admin`.

```http
PUT /user/2

username=admin
```

### POST /login

The request used the following parameters:

```text
username=thm
password=letmein
```

Request:

```http
POST /login
```

## What I Learned

This room helped me understand the fundamentals of how web browsers communicate with web servers using HTTP.

I learned how URLs are structured, how HTTP requests and responses work, the purpose of common HTTP methods, how status codes indicate the result of a request, how headers provide additional information, and how cookies can be used to maintain information between requests.

I also practiced creating different HTTP requests using the provided request emulator.
