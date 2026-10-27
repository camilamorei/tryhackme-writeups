# OWASP Top 10 2025: Insecure Data Handling

## Overview

This room explores insecure data handling vulnerabilities from the OWASP Top 10 2025. It focuses on cryptographic failures, server-side template injection, and insecure deserialization.

## Topics Covered

- Cryptographic Failures
- Server-Side Template Injection (SSTI)
- Insecure Deserialization
- Sensitive data exposure
- Risks associated with unsafe data processing

## Task 1: Introduction

Introduced the main concepts of insecure data handling and the security risks associated with improperly protecting or processing data.

Answer: No answer needed

## Task 2: A04 Cryptographic Failures

Explored cryptographic weaknesses that can expose sensitive information when data is not properly protected.

Flag:

```text
THM{WEAK_CRYPTO_FLAG}
```

## Task 3: A05 Injection

Investigated Server-Side Template Injection (SSTI), a vulnerability that occurs when untrusted input is processed by a template engine without proper safeguards.

Flag:

```text
THM{SSTI_FLAG_OBTAINED}
```

## Task 4: A08 Software or Data Integrity Failures

Examined insecure deserialization and the risks of processing untrusted serialized data. Unsafe deserialization can allow attackers to manipulate application behavior or execute unintended code.

Flag:

```text
THM{INSECURE_DESERIALIZATION}
```

## Key Takeaways

- Cryptographic controls must be implemented correctly to protect sensitive data.
- User-controlled input should never be trusted when processed by template engines.
- Deserializing untrusted data can introduce serious security vulnerabilities.
- Secure data handling requires validation, safe processing, and appropriate security controls.

## Conclusion

This room demonstrated how weaknesses in cryptography, template processing, and deserialization can compromise application security. Understanding these vulnerabilities helps identify insecure data handling practices and apply safer development techniques.
