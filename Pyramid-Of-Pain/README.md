# Pyramid Of Pain

## Room Information

- Platform: TryHackMe
- Difficulty: Easy
- Category: Cybersecurity, Threat Intelligence
- Room URL: https://tryhackme.com/room/pyramidofpainax

## Introduction

The Pyramid of Pain is a cybersecurity model that ranks indicators of compromise according to how difficult they are for an attacker to change.

The higher an indicator appears on the pyramid, the more effort an attacker must make to evade detection.

The pyramid includes the following levels:

1. Hash Values
2. IP Addresses
3. Domain Names
4. Network and Host Artifacts
5. Tools
6. Tactics, Techniques, and Procedures (TTPs)

## Task 1: Introduction

The Pyramid of Pain helps security professionals improve threat hunting, incident response, and threat intelligence.

No answer required.

## Task 2: Hash Values

Hash values are unique strings generated from data. Security analysts can use file hashes to identify known malicious files.

Question: What is the filename of the sample associated with the provided hash?

Answer: `Sales_Receipt 5606.xls`

## Task 3: IP Address

IP addresses identify devices communicating over a network. Blocking malicious IP addresses can prevent connections to known attacker infrastructure.

Answers:

- First IP address contacted by the malicious process: `50.87.136.52`
- First domain contacted by the malicious process: `craftingalegacy.com`

## Task 4: Domain Names

Domain names provide human-readable addresses for accessing websites. Attackers may use suspicious domains, shortened URLs, or Unicode characters to impersonate legitimate websites.

Answers:

- First suspicious domain request: `craftingalegacy.com`
- Term for an address used to access websites: `Domain Name`
- Attack that uses Unicode characters to imitate a known domain: `Punycode attack`
- Redirected destination of the shortened URL: `https://tryhackme.com/`

## Task 5: Host Artifacts

Host artifacts are traces left on a computer by suspicious or malicious activity. These can include executable files, registry changes, and unusual process behavior.

Answers:

- IP address contacted by `regidle.exe` on port 8080: `96.126.101.6`
- Name of the dropped executable: `G_jugk.exe`
- Number of VirusTotal vendors that detected the file as malicious: `9`

## Task 6: Network Artifacts

Network artifacts are observable characteristics of network traffic that can help identify malicious activity. Examples include HTTP requests, User-Agent strings, and communication patterns.

Answers:

- Browser associated with the displayed User-Agent string: `Internet Explorer`
- Number of POST requests shown in the PCAP screenshot: `6`

A User-Agent string can provide information about the client software involved in a network request. Analysts can use this information as one indicator when investigating suspicious traffic.

## Task 7: Tools

Attackers use tools to carry out activities such as creating malware, establishing command-and-control communication, and stealing data.

Fuzzy hashing helps analysts compare files and identify similarities even when the files are not identical.

Answers:

- Method used to determine similarity between files: `Fuzzy Hashing`
- Alternative name for fuzzy hashes: `context triggered piecewise hashes`

## Task 8: Tactics, Techniques, and Procedures

TTPs describe how attackers operate, including their tactics, techniques, and procedures. Detecting these behaviors can make it harder for attackers to continue their operations.

Answers:

- Number of techniques under the Exfiltration category in the MITRE ATT&CK Matrix: `9`
- Commercial remote access tool used by the Chimera group: `Cobalt Strike`

## Task 9: Practical: The Pyramid of Pain

The practical exercise requires placing indicators and behaviors into the correct levels of the Pyramid of Pain.

The correct categories are:

- File hashes: signatures used to identify files.
- IP addresses: addresses associated with attacker infrastructure.
- Domain names: domains used for malicious communication.
- Network and host artifacts: traces left on systems or within network traffic.
- Tools: software used by attackers.
- TTPs: the tactics, techniques, and procedures used to achieve their objectives.

Flag: `THM{PYRAMIDS_COMPLETE}`

## Task 10: Conclusion

This room introduced the Pyramid of Pain and explained how different indicators can help security teams detect malicious activity.

The main lesson is that detecting attacker behavior and TTPs can be more difficult for adversaries to evade than detection based only on file hashes or IP addresses.

Understanding these indicators is useful for threat hunting, incident response, and security operations center (SOC) analysis.

## Skills Learned

- Understanding the Pyramid of Pain
- Identifying file hashes and malicious IP addresses
- Investigating suspicious domains
- Recognizing host and network artifacts
- Understanding fuzzy hashing
- Exploring the MITRE ATT&CK framework
- Learning about attacker tools and TTPs

## References

- TryHackMe: https://tryhackme.com/room/pyramidofpainax
- MITRE ATT&CK: https://attack.mitre.org/
- VirusTotal: https://www.virustotal.com/
- ANY.RUN: https://any.run/
