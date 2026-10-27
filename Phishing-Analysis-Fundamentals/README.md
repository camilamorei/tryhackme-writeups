# Phishing Analysis Fundamentals

## Overview

Phishing Analysis Fundamentals introduces the techniques used to investigate suspicious emails and identify potential security threats. The room covers email structure, delivery protocols, header analysis, attachment inspection, and common phishing techniques.

The practical exercises involve examining raw email files to identify sender information, suspicious IP addresses, attachment details, and signs of impersonation.

## Objectives

- Understand the structure of email addresses.
- Learn how SMTP, POP3, IMAP, and DNS support email delivery.
- Analyze email headers and message source data.
- Inspect email bodies and attachments.
- Recognize common phishing techniques.
- Identify suspicious sender addresses, IP addresses, and mail servers.
- Understand Business Email Compromise (BEC).

## Task 2: The Email Address

An email address consists of a username, an @ symbol, and a domain name.

Answer:

- Domain: `tryhatme.com`

The domain identifies the destination domain associated with the recipient's email address.

## Task 3: Email Delivery

Email communication relies on several protocols and services.

Answers:

- Sending emails: SMTP
- Looking up a recipient domain's mail server: DNS
- Accessing and synchronizing emails across multiple devices: IMAP

SMTP is used to send email messages. DNS helps locate the recipient's mail server. IMAP synchronizes mailbox contents across devices, while POP3 typically downloads messages to a client.

## Task 4: Email Headers

Email headers contain metadata that helps analysts investigate the origin and routing of a message.

Answers:

- Subject: `Help protect your budget by protecting your home`
- X-Originating-IP: `43.255.56.161`

Important header fields include:

- From: The sender address displayed in the message.
- To: The intended recipient.
- Reply-To: The address used when replying.
- Subject: The message subject.
- Date: The message timestamp.
- X-Originating-IP: An IP address associated with the message's origin, when provided.

Header information should be evaluated alongside other evidence because individual fields can be missing or manipulated.

## Task 5: Email Body

Email bodies may contain plain text, HTML, embedded links, and attachments. Inspecting the raw source can reveal information that is not immediately visible in the email client.

Answers:

- Attachment Content-Type: `application/pdf`
- Attachment filename: `zmqpalgh.pdf`

The attachment's Base64-encoded content can be decoded to reconstruct the original file for safe analysis.

Security analysts should inspect attachments in an isolated environment and avoid opening suspicious files on their primary system.

## Task 6: Types of Phishing

Phishing attacks use social engineering to persuade victims to reveal sensitive information, open malicious attachments, or visit attacker-controlled websites.

Common types include:

- Spam: Unsolicited bulk messages.
- Phishing: Messages designed to deceive recipients.
- Spear phishing: Targeted phishing against a specific individual or organization.
- Whaling: Phishing aimed at senior executives.
- Smishing: Phishing through SMS messages.
- Vishing: Phishing through voice calls.

### Investigation Answers

- Spoofed organization: Home Depot
- Sender email address: `support@teckbe.com`
- Defanged X-Originating-IP: `103[.]234[.]236[.]83`
- Mail server in the Authentication-Results header: `atlas102.free.mail.gq1.yahoo.com`

### Safe Analysis Practices

- Inspect sender addresses and email headers.
- Compare displayed links with their actual destinations.
- Defang suspicious URLs and IP addresses to prevent accidental interaction.
- Treat unexpected attachments with caution.
- Verify suspicious requests through an independent, trusted communication channel.

## Task 7: Conclusion

Answer:

- BEC: Business Email Compromise

Business Email Compromise is a type of fraud in which attackers use compromised or impersonated business email accounts to deceive employees into transferring money, sharing sensitive information, or performing unauthorized actions.

## Key Takeaways

- SMTP sends email, DNS locates mail servers, and IMAP synchronizes messages across devices.
- Email headers provide useful evidence for investigating suspicious messages.
- Raw message source can reveal IP addresses, authentication details, and attachment metadata.
- Phishing emails may impersonate legitimate organizations or use deceptive sender addresses.
- Defanging suspicious indicators helps prevent accidental clicks during analysis.
- Business Email Compromise can cause financial losses and expose confidential information.

## Conclusion

This room develops foundational email investigation skills for cybersecurity analysts. Understanding email delivery, examining message headers, inspecting attachments, and recognizing phishing indicators helps defenders investigate suspicious messages and reduce the risk of social engineering attacks.
