# ItsyBitsy

## Overview

This room focuses on investigating a potential Command and Control (C2) communication alert using network connection logs in Kibana. The investigation involves identifying suspicious activity associated with a user from the HR department and tracing a connection to a file-sharing service used to host malicious content.

## Learning Objectives

- Investigate potential C2 communication alerts.
- Analyze HTTP connection logs in Kibana.
- Identify suspicious IP addresses and URLs.
- Recognize the abuse of legitimate Windows binaries.
- Investigate file-sharing services used in malware communication.
- Extract relevant indicators of compromise from network logs.

## Topics Covered

### Network Log Analysis

Examining connection logs from the `connection_logs` index to identify suspicious network activity during March 2022.

### Living Off the Land

Understanding how legitimate Windows utilities, such as `bitsadmin`, can be abused to download files from external servers.

### Command and Control Communication

Investigating connections to Pastebin and identifying URLs associated with potentially malicious activity.

### Indicators of Compromise

Identifying suspicious IP addresses, URLs, and accessed files to support incident investigation.

## Key Takeaways

- Network connection logs can help identify suspicious communication patterns.
- Legitimate system utilities can be abused for malicious purposes.
- File-sharing platforms may be used to host content associated with malware activity.
- Investigators should correlate IP addresses, URLs, and file access events to understand a potential compromise.

## Tools and Technologies

- Kibana
- Elastic connection logs
- HTTP traffic analysis
- Windows `bitsadmin`

## Conclusion

The ItsyBitsy room demonstrates how a security analyst can investigate a potential C2 alert using network connection logs. By examining HTTP activity and correlating suspicious indicators, analysts can identify potentially malicious communication and gather evidence for further investigation.
