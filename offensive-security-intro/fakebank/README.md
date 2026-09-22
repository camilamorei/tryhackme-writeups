# TryHackMe — Offensive Security Intro: FakeBank

## Overview

This write-up documents my work on the FakeBank room from TryHackMe's Offensive Security Intro path.

The exercise introduced basic web application reconnaissance and demonstrated how an exposed, unprotected endpoint can provide access to sensitive functionality.

---

## 1. Directory Enumeration with DIRB

The first step was to enumerate the web application and discover directories that were not necessarily linked from the main page.

I used DIRB with the following command:

```bash
dirb http://fakebank.thm
```

DIRB performs web content enumeration by testing common directory and file names against the target.

The scan revealed multiple URLs, including the `/bank-transfer` endpoint.

### Key observation

The `/bank-transfer` page appeared to expose functionality related to bank transfers and internal banking operations.

This demonstrates an important security concept:

> A resource does not become secure simply because it is hidden or difficult to find.

If an endpoint is accessible without proper authentication or authorization, an attacker who discovers it may still be able to interact with it.

---

## 2. Discovering the Bank Transfer Page

The discovered endpoint was:

```text
http://fakebank.thm/bank-transfer
```

The page provided access to a bank-transfer interface.

This was particularly interesting because it appeared to be an internal/admin function rather than a normal customer-facing page.

---

## 3. Testing the Bank Transfer Functionality

The exercise provided a verified bank account number:

```text
8881
```

The account belonged to:

```text
Mrs G. Benjamin
```

The account initially had a negative balance:

```text
-$1,232.32
```

Using the exposed bank-transfer functionality, I deposited at least $2,000 into account `8881`.

This caused the account balance to become positive and triggered the success message required by the room.

---

## 4. Security Question

The exercise asked how FakeBank could make the bank-transfer page more secure.

The available options were:

* Require login
* Make the URL harder to guess
* Move the page to another server

The appropriate security mechanism is:

```text
Require login
```

### Why?

Making a URL harder to guess is not an authentication mechanism.

For example:

```text
/bank-transfer
```

could theoretically be changed to something harder to discover, but anyone who obtains the new URL could still access the page.

Authentication requires the user to prove their identity before accessing sensitive functionality.

Authorization should also be implemented so that authenticated users can only perform actions they are actually permitted to perform.

---

## 5. Important Security Lessons

### Hidden does not mean secure

An administrator page should not rely on secrecy of its URL.

Directory enumeration tools such as DIRB can discover resources that developers may assume are hidden.

### Authentication

Sensitive functionality should require authentication.

For example:

```text
User → Login → Authentication → Bank Transfer
```

rather than:

```text
User → /bank-transfer → Bank Transfer
```

### Authorization

Authentication alone is not always sufficient.

The application should also verify whether the authenticated user has permission to perform the requested operation.

### Attack surface discovery

Directory enumeration is a basic reconnaissance technique that can reveal:

* Administrative panels
* Login pages
* Backup files
* Configuration files
* API endpoints
* Internal functionality

---

## Commands Used

### DIRB

```bash
dirb http://fakebank.thm
```

---

## Skills Practiced

* Web reconnaissance
* Directory enumeration
* DIRB
* Identifying exposed web endpoints
* Understanding authentication
* Understanding authorization
* Recognizing insecure direct access to functionality
* Basic web application security

---

## Conclusion

The FakeBank exercise demonstrated how an exposed web endpoint can provide access to sensitive functionality when proper access controls are missing.

The main lesson from this exercise is that security through obscurity is not a substitute for authentication and authorization.

Sensitive banking functionality should be protected by proper access controls rather than relying on an endpoint being difficult to discover.

---

## TryHackMe

Room: Offensive Security Intro — FakeBank

Platform: TryHackMe

Focus: Web reconnaissance and basic web application security
