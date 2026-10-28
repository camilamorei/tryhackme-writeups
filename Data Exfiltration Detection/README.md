# Data Exfiltration Detection

## Overview

This room explores how attackers steal sensitive data from compromised systems and how Security Operations Center (SOC) analysts can detect data exfiltration attempts.

The exercises cover DNS tunneling, FTP transfers, HTTP uploads, ICMP tunneling, network traffic analysis, and log correlation using Splunk.

## Task 1: Introduction

Data exfiltration is the unauthorized transfer of sensitive information from a system or network to an external destination.

Attackers may perform data exfiltration for financial gain, espionage, extortion, sabotage, or further exploitation of a compromised environment.

SOC analysts need to identify suspicious transfers before sensitive information leaves the organization.

## Task 2: Lab Connection

The lab provides packet captures and log files in the `data_exfil` directory on the Desktop.

The Splunk instance is accessible through port `8000` on the lab machine. The relevant events are stored in the `data_exfil` index.

For Splunk investigations, select the `All time` range to include the complete dataset.

## Task 3: Data Exfiltration Overview, Techniques, and Indicators

Attackers can exfiltrate data through several channels, including HTTP, HTTPS, FTP, DNS, ICMP, cloud storage services, and removable media.

Common stages include locating sensitive information, collecting and staging files, compressing or encoding data, transferring it outside the network, and coordinating the transfer through command and control infrastructure.

Important indicators include:

- Unusually large outbound transfers.
- Repeated uploads to unfamiliar external destinations.
- Long or encoded DNS queries.
- Large HTTP POST requests.
- Unexpected FTP uploads or suspicious credentials.
- Large ICMP payloads.
- Suspicious processes accessing sensitive files before initiating network connections.

Answer:

- Technique associated with HTTP-based data exfiltration: `Network-based`

## Task 4: Detection: Data Exfiltration through DNS Tunneling

DNS tunneling abuses DNS queries and responses to carry encoded data through a protocol that is commonly allowed by network security controls.

Attackers can encode information in subdomain labels or DNS records and transfer it through repeated requests to an attacker-controlled domain.

### Wireshark Filters

Show DNS traffic:

```text
dns
```

Show DNS queries without responses:

```text
dns.flags.response == 0
```

Find DNS packets with larger frame lengths:

```text
dns && frame.len > 70
```

Filter queries containing the suspicious domain:

```text
dns && dns.qry.name contains "tunnelcorp.net"
```

### Splunk Queries

Show DNS events:

```spl
index="data_exfil" sourcetype="DNS_logs"
```

Count DNS queries by source IP:

```spl
index="data_exfil" sourcetype="DNS_logs"
| stats count by src_ip
```

Identify frequently queried domains:

```spl
index="data_exfil" sourcetype="DNS_logs"
| stats count by query
| sort -count
```

Find unusually long DNS query names:

```spl
index="data_exfil" sourcetype="DNS_logs"
| where len(query) > 30
```

Answers:

- Suspicious domain receiving DNS traffic: `tunnelcorp.net`
- Number of suspicious DNS tunneling events: `315`
- Local IP generating the maximum number of suspicious requests: `192.168.1.103`

## Task 5: Detection: Data Exfiltration through FTP

FTP is used to transfer files between systems, but traditional FTP traffic may expose credentials and file transfer commands in cleartext.

Attackers can abuse FTP to upload sensitive files using compromised accounts or unauthorized guest access.

Relevant FTP commands include:

- `USER`: Supplies a username.
- `PASS`: Supplies a password.
- `STOR`: Uploads a file.
- `RETR`: Downloads a file.

### Wireshark Filters

Show FTP control and data traffic:

```text
ftp || ftp-data
```

Show username and password commands:

```text
ftp.request.command == "USER" || ftp.request.command == "PASS"
```

Search for file uploads:

```text
ftp contains "STOR"
```

Search for CSV-related traffic:

```text
ftp contains "csv"
```

Focus on larger FTP packets:

```text
ftp && frame.len > 90
```

Following the TCP stream allows analysts to inspect the commands, filenames, and data associated with a transfer.

Answers:

- Number of connections observed from the guest account: `5`
- Customer-related file exfiltrated from the root account: `customer_data.xlsx`
- Internal IP sending the largest payload to an external IP: `192.168.1.105`

The flag for this task is intentionally omitted. Recover it by inspecting the FTP stream transferring the CSV file.

## Task 6: Detection: Data Exfiltration via HTTP

HTTP is commonly abused for data exfiltration because it resembles normal web traffic. Attackers can send sensitive information through POST request bodies, URL parameters, custom headers, or multipart uploads.

Detection requires examining request sizes, destinations, upload frequency, and the context of the originating host.

### Splunk Queries

Show HTTP logs:

```spl
index="data_exfil" sourcetype="http_logs"
```

Filter POST requests:

```spl
index="data_exfil" sourcetype="http_logs" method=POST
```

Calculate transfer statistics by domain:

```spl
index="data_exfil" sourcetype="http_logs" method=POST
| stats count avg(bytes_sent) max(bytes_sent) min(bytes_sent) by domain
| sort -count
```

Identify POST requests with large payloads:

```spl
index="data_exfil" sourcetype="http_logs" method=POST bytes_sent > 600
| table _time src_ip uri domain dst_ip bytes_sent
| sort - bytes_sent
```

### Wireshark Filters

Show HTTP traffic:

```text
http
```

Show POST requests:

```text
http.request.method == "POST"
```

Filter larger POST packets:

```text
http.request.method == "POST" and frame.len > 500
```

Narrow the search to even larger frames:

```text
http.request.method == "POST" and frame.len > 750
```

After identifying a suspicious request, use `Follow HTTP Stream` to inspect the transferred content and search for evidence of sensitive data.

Answers:

- Internal compromised host used to exfiltrate sensitive data: `192.168.1.103`

The flag for this task is intentionally omitted. Recover it by inspecting the HTTP stream containing the exfiltrated data.

## Task 7: Detection: Data Exfiltration via ICMP

ICMP is normally used for network diagnostics and error reporting. Attackers can abuse its payload to transfer encoded information to a remote system.

Suspicious indicators include large ICMP packets, frequent echo requests, unusual payload patterns, and repeated communication with an unfamiliar external address.

### Wireshark Filters

Show all ICMP traffic:

```text
icmp
```

Show ICMP Echo Requests:

```text
icmp.type == 8
```

Identify larger ICMP Echo Requests:

```text
icmp.type == 8 and frame.len > 100
```

Look for ICMP packets with large data payloads:

```text
icmp && data.len > 64
```

Inspect suspicious packet payloads to identify encoded data and recover the exfiltrated content.

The flag for this task is intentionally omitted. Recover it by examining the suspicious ICMP packets and their payloads in the provided capture file.

## Task 8: Conclusion

This room demonstrates how attackers can use common network protocols to transfer sensitive data outside an organization.

The exercises cover detection through packet captures and SIEM log analysis, with practical examples involving DNS tunneling, FTP transfers, HTTP POST requests, and ICMP payloads.

## Key Takeaways

- Data exfiltration can occur through legitimate protocols and services.
- DNS tunneling may be indicated by long, encoded queries and unusually high query volumes.
- FTP traffic can expose credentials, upload commands, and transferred files.
- Large or unusual HTTP POST requests may indicate data exfiltration.
- Large ICMP payloads can conceal encoded information.
- Wireshark helps inspect packet contents and follow protocol streams.
- Splunk helps aggregate, filter, and correlate network logs.
- Correlating multiple data sources provides stronger evidence than relying on a single alert.
