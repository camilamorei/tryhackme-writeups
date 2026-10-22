# TryHackMe: IDS Fundamentals

## Room Overview

This room introduces Intrusion Detection Systems (IDS), their purpose, detection methods, and the use of Snort to analyze network traffic.

## What I Learned

- The difference between IDS and IPS.
- The difference between NIDS and HIDS.
- Signature-based, anomaly-based, and hybrid detection.
- Snort operating modes and rule syntax.
- How to analyze PCAP files using Snort.
- How to identify suspicious network traffic and inspect alert messages.

## Task Answers

### Snort Rules

1. Main Snort directory: `/etc/snort`
2. Rule field indicating the revision number: `rev`
3. Protocol defined in the sample rule: `ICMP`
4. File containing custom Snort rules: `local.rules`

### PCAP Analysis

1. IP address of the machine that attempted an SSH connection: `10.11.90.211`
2. Other detected rule message: `Ping Detected`
3. SID of the SSH detection rule: `1000002`

## Commands Used

Navigate to the Snort directory:

```bash
cd /etc/snort
```

Analyze the PCAP file with Snort:

```bash
sudo snort -r Intro_to_IDS.pcap -c /etc/snort/snort.conf -A console
```

## Key Takeaways

This room helped me understand how intrusion detection systems monitor network traffic and identify suspicious activity. I also learned how Snort rules work and how PCAP analysis can help investigators identify potential attacks, including SSH connection attempts and ping activity.

## Conclusion

Understanding IDS and learning to analyze network traffic are important skills in cybersecurity, particularly in network monitoring, incident response, and digital forensics.
