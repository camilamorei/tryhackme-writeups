# Phishing Emails in Action

## Overview

This room explores phishing emails and the techniques attackers use to deceive recipients, steal credentials, and deliver malicious files.

The exercises focus on analyzing email headers, identifying sender spoofing, inspecting suspicious links, understanding tracking pixels, and recognizing malicious attachments.

## Task 1: Introduction

This task introduces phishing email analysis and the importance of investigating suspicious messages before interacting with their content.

## Task 2: Cancel Your Order

This email impersonates PayPal and claims that a transaction was made to pressure the recipient into cancelling an order.

The sender address does not match the legitimate PayPal domain. The email also contains a shortened URL that hides the destination of the cancellation button.

Answer:
- Merchant: `Amazing Stuff`

Key takeaways:
- Display names can be spoofed.
- Unexpected payment notifications can be used for social engineering.
- Shortened URLs should be investigated before being opened.

## Task 3: Track Your Package

This email impersonates a distribution center and uses a fake shipping notification to encourage the recipient to follow a tracking link.

The message contains a tracking pixel that can notify the sender when the email is opened. The hyperlink points to a suspicious domain unrelated to a legitimate shipping service.

Answer:
- Defanged root domain: `devret[.]xyz`

Key takeaways:
- Tracking pixels can reveal email engagement.
- Sender domains should be checked carefully.
- Defanging URLs helps prevent accidental navigation to suspicious destinations.

## Task 4: Download Document Here

This email uses a document-sharing notification and an expiration deadline to create urgency.

The link redirects through pages impersonating trusted services before reaching a fake login portal designed to collect credentials.

Answer:
- Attack type: `Credential Harvesting`

Key takeaways:
- Redirect chains can conceal malicious destinations.
- Fake login portals can steal usernames and passwords.
- Trusted branding does not guarantee that a page is legitimate.

## Task 5: Your Account Is on Hold

This email impersonates Netflix billing services and claims that the recipient's account is on hold.

The display name contains a deliberate misspelling, and the actual sender address belongs to an unrelated domain. The attached PDF contains a link intended to direct the recipient to a fraudulent payment page.

Answer:
- Actual sender address: `z99@musacombi.online`

Key takeaways:
- Inspect the actual sender address instead of trusting the display name.
- Unexpected attachments may contain malicious links.
- Verify billing notifications through the official service website.

## Task 6: Your Recent Purchase

This email impersonates Apple Support and uses a purchase notification to make the recipient investigate an alleged transaction.

The message has an empty body and relies on a suspicious Microsoft Word template attachment containing a clickable image.

Answers:
- BCC: `Blind Carbon Copy`
- Attachment extension: `.dot`

Key takeaways:
- BCC hides recipients from other recipients.
- Unexpected document templates can contain dangerous content.
- Links embedded in images and documents should be inspected carefully.

## Task 7: Scheduled Shipment

This email impersonates DHL Express and uses a shipping notification to encourage the recipient to open an Excel attachment.

The attachment contains a link that attempts to download or execute a suspicious executable.

Answer:
- Executable name: `regasms.exe`

Key takeaways:
- Office documents can be used to deliver malicious payloads.
- Inconsistent language, locations, and sender information are warning signs.
- Suspicious executables should never be run on a personal system.

## Conclusion

This room demonstrates how phishing campaigns combine social engineering, sender spoofing, suspicious URLs, tracking pixels, credential harvesting, and malicious attachments.

The main lesson is to verify sender identities, inspect email headers, analyze links safely, and treat unexpected attachments with caution.

These techniques are useful for identifying phishing attempts during security monitoring and incident response.
