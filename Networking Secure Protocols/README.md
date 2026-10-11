# Networking Secure Protocols

## Overview

This room explored secure network protocols and how encrypted traffic can be analyzed using Wireshark. It demonstrated how to inspect network packets, identify application-layer requests, and understand how TLS decryption can expose traffic contents when the appropriate decryption information is available.

## Topics Covered

- HTTPS and TLS
- HTTP/2 traffic analysis
- Wireshark display filters
- TLS protocol preferences
- Decrypting encrypted network traffic
- Inspecting HTTP request headers and form data
- Analyzing POST requests and server responses
- Understanding the risks of transmitting credentials

## Tools Used

- Wireshark
- Packet capture files (PCAP)
- Wireshark TLS protocol preferences

## Practical Analysis

### Filtering HTTP/2 Traffic

Display filters can help isolate specific application protocols and reduce the amount of traffic displayed.

Example filter:

```text
http2
```

To find HTTP POST requests, the following filter can be used:

```text
http2.headers.method == "POST"
```

### Configuring TLS Decryption

Wireshark provides TLS protocol preferences that allow analysts to configure decryption settings when the required key material is available.

The relevant settings can be accessed by opening a packet's context menu and navigating to:

`Protocol Preferences → Transport Layer Security`

The `(Pre)-Master-Secret log filename` field can be used to specify a TLS key log file when one is available and compatible with the captured traffic.

### Inspecting HTTP/2 Requests

After decrypting the traffic, HTTP/2 streams can reveal request metadata, including:

- HTTP method
- Authority and destination hostname
- Request path
- User-Agent
- Content-Type
- Form parameters in the request body
- HTTP response status and headers

During the investigation, a POST request to a login endpoint contained form parameters in the decrypted request body. This demonstrated how sensitive information can become visible during packet analysis when encrypted traffic is successfully decrypted.

## Key Takeaways

- HTTPS relies on TLS to protect data transmitted between clients and servers.
- Encrypted packet captures cannot normally be read as plaintext without suitable decryption material.
- Wireshark can reconstruct and display decrypted application-layer traffic when configured correctly.
- HTTP/2 uses headers and streams to represent application requests and responses.
- Display filters make it easier to identify relevant packets in large captures.
- Decrypted traffic may expose sensitive information, so packet captures and key log files must be handled securely.

## Conclusion

This room demonstrated how to investigate encrypted network traffic using Wireshark and how TLS decryption can help analysts inspect HTTP/2 requests. These skills are useful in network troubleshooting, incident response, and security investigations, particularly when identifying sensitive data exposure and understanding application behavior.
