# Wireshark: The Basics

## Overview

This room introduces Wireshark, a network protocol analyzer used to capture, inspect, and analyze network traffic. It covers the interface, packet navigation, capture file properties, expert information, display filters, and stream reconstruction.

## Topics Covered

- Wireshark interface and packet analysis
- Capture file properties and metadata
- Packet details and packet comments
- Packet navigation and searching
- Exporting objects from packet captures
- Expert Information and warning analysis
- Display filters and protocol filtering
- Apply as Filter and Prepare as Filter
- Conversation filters and conversation colourisation
- Applying packet fields as columns
- Following HTTP streams to reconstruct application-level traffic

## Tools Used

- Wireshark
- Exercise.pcapng
- HTTP object export
- Display filter bar

## Practical Exercises

### Capture File Analysis

- Inspected capture file comments and metadata.
- Identified the total number of packets.
- Examined the capture file's SHA-256 hash.
- Used packet details to inspect protocol fields and packet information.

### Packet Navigation

- Searched packet details for specific strings.
- Inspected packet comments for investigation instructions.
- Exported objects from HTTP traffic.
- Examined Expert Information to identify packet warnings.

### Packet Filtering

- Applied display filters using the right-click menu.
- Used the `http` display filter to isolate HTTP traffic.
- Followed an HTTP stream to reconstruct application-level communication.
- Examined web server responses to identify information returned by the application.

## Key Takeaways

- Wireshark helps analysts inspect network traffic at different protocol layers.
- Capture filters and display filters serve different purposes: capture filters limit what is collected, while display filters control which captured packets are shown.
- Packet details provide information about protocol fields and values.
- Export Objects can extract files transferred through supported protocols.
- Expert Information helps identify warnings and other noteworthy network events.
- Following a stream reconstructs communication in a more readable application-level format.
- Applying filters and adding columns can make investigations more efficient.

## Conclusion

This room provided a foundation for using Wireshark during network traffic investigations. I practised navigating packet captures, examining packet metadata, extracting transferred objects, applying display filters, and reconstructing HTTP communication.

These skills are useful for network troubleshooting, traffic analysis, and cybersecurity investigations.
