# Snapped Phish-ing Line

## Overview

This TryHackMe room focuses on investigating a phishing campaign targeting employees at SwiftSpend Financial. The investigation involves analyzing suspicious emails, tracing phishing URLs, retrieving an exposed phishing kit, and identifying indicators of compromise.

## Objectives

- Analyze suspicious emails and identify the recipients and sender.
- Investigate redirection URLs and identify the impersonated organization.
- Retrieve and analyze an exposed phishing kit.
- Use VirusTotal to investigate file hashes and threat classifications.
- Examine captured credential logs.
- Identify the attacker's credential collection address.
- Decode a secret value from an encoded flag file.

## Task 1: A Series of Suspicious Emails

### Email Investigation

| Question | Answer |
|---|---|
| Recipient of the "Quote for Services Rendered" email | `William McClean` |
| Phishing email sender | `Accounts.Payable@groupmarketingonline.icu` |
| Root domain of the redirection URL | `kennaroads.buzz` |
| Impersonated company | `Microsoft` |

### Phishing Kit Analysis

| Question | Answer |
|---|---|
| Archive filename | `Update365.zip` |
| SHA256 hash | `ba3c15267393419eb08c7b2652b8b6b39b406ef300ae8a18fee4d16b19ac9686` |
| Additional VirusTotal threat category | `Trojan` |
| Number of files in the archive | `49` |

### Credential Investigation

| Question | Answer |
|---|---|
| User who submitted credentials more than once | `michael.ascot@swiftspend.finance` |
| Attacker's credential collection email | `m3npat@yandex.com` |
| Decoded secret value | `THM{pL4y_w1Th_tH3_URL}` |

## Investigation Methodology

### 1. Review the Email Samples

Inspect the emails in the `phish-emails` directory. Review the sender, recipient, subject, and attachment information to identify suspicious characteristics and determine the scope of the campaign.

### 2. Investigate the Redirect URL

Examine the attachment associated with Zoe Duncan's email. Identify the URL embedded in the file and determine its root domain. Open the attachment in the isolated lab environment to inspect the impersonated login page.

### 3. Retrieve the Phishing Kit

Navigate to the website's `/data` directory and locate the exposed archive. Download the archive for further analysis within the lab environment.

### 4. Calculate the SHA256 Hash

Use the following command to calculate the archive's SHA256 hash:

```bash
sha256sum Update365.zip
```

Search the resulting hash on VirusTotal to review threat classifications, file details, and the number of files contained in the archive.

### 5. Analyze Captured Credentials

Inspect the logs in `/data/Update365/` to identify users who submitted credentials multiple times. Examine the phishing kit's `submit.php` file to determine the destination used to collect compromised credentials.

### 6. Decode the Flag

Locate `flag.txt` on the phishing website. Use CyberChef to apply the Base64 decoding operation followed by a character reversal to recover the secret value.

## Indicators of Compromise

- Suspicious sender domain: `groupmarketingonline.icu`
- Phishing domain: `kennaroads.buzz`
- Phishing kit archive: `Update365.zip`
- Credential collection address: `m3npat@yandex.com`
- SHA256: `ba3c15267393419eb08c7b2652b8b6b39b406ef300ae8a18fee4d16b19ac9686`

## Key Takeaways

- Phishing campaigns can impersonate trusted organizations to steal credentials.
- Email headers, attachments, and embedded URLs provide valuable investigation artifacts.
- Exposed directories can reveal phishing kits and attacker infrastructure.
- File hashes can be used to investigate suspicious files through threat intelligence services.
- Credential logs can help identify affected users and determine the scope of an incident.
- Analyzing collection scripts can reveal where stolen credentials are sent.

## Tools Used

- Web browser
- Linux terminal
- `sha256sum`
- VirusTotal
- CyberChef

## Conclusion

This investigation demonstrates how email analysis, URL investigation, threat intelligence, and phishing kit analysis can be combined to investigate a credential theft campaign. Identifying the phishing infrastructure and exposed collection mechanisms helps defenders understand the attack and develop appropriate mitigation measures.
