# DNS in Detail

TryHackMe room focused on understanding how the Domain Name System (DNS) works, including domain hierarchy, DNS record types, DNS requests, and practical DNS queries.

Room: https://tryhackme.com/room/dnsindetail

## Task 1: What is DNS?

DNS stands for:

`Domain Name System`

DNS is used to translate domain names into IP addresses, allowing devices to locate services on a network.

## Task 2: Domain Hierarchy

DNS uses a hierarchical structure made up of different levels, including the root domain, Top-Level Domains (TLDs), domains, and subdomains.

Maximum subdomain length:

`63`

Forbidden character:

`_`

Maximum domain name length:

`253`

`.co.uk` is a:

`ccTLD`

## Task 3: Record Types

DNS records contain different types of information about a domain.

Record used for email routing:

`MX`

Record used for IPv6 addresses:

`AAAA`

## Task 4: Making A Request

When a device makes a DNS request, different DNS servers can be involved in finding the required information.

The field that determines how long a DNS record can be cached:

`TTL`

The DNS server usually provided by an ISP:

`Recursive DNS Server`

The DNS server that holds all the records for a domain:

`Authoritative DNS Server`

## Task 5: Practical

The practical task involved using the provided website to create DNS queries and inspect the results of different DNS record types.

CNAME of `shop.website.thm`:

`shops.myshopify.com`

TXT record of `website.thm`:

`THM{7012BBA60997F35A9516C2E16D2944FF}`

Numerical priority value for the MX record:

`30`

IP address for the A record of `www.website.thm`:

`10.10.10.10`

## DNS Record Types

| Record | Purpose |
|---|---|
| A | Maps a domain to an IPv4 address |
| AAAA | Maps a domain to an IPv6 address |
| CNAME | Creates an alias for another domain |
| MX | Specifies mail servers and their priority |
| TXT | Stores text information associated with a domain |

## Key Concepts

DNS stands for Domain Name System.

DNS translates domain names into IP addresses.

A records are used for IPv4 addresses.

AAAA records are used for IPv6 addresses.

CNAME records point a domain to another domain name.

MX records specify mail servers and their priority.

TXT records store text associated with a domain.

TTL determines how long DNS information can be cached.

Recursive DNS servers perform DNS queries on behalf of clients.

Authoritative DNS servers contain the official DNS records for a domain.

ccTLD stands for Country Code Top-Level Domain.

## What I Learned

This room helped me understand how DNS works and how different DNS record types are used.

I learned about the DNS hierarchy, A, AAAA, CNAME, MX, and TXT records, as well as the difference between recursive and authoritative DNS servers.

The practical section allowed me to perform DNS queries and inspect the information returned by different record types.
