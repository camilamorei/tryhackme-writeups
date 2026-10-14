# Cryptography Basics

TryHackMe room: Cryptography Basics

## Task 1: Introduction

This room introduces the fundamental concepts of cryptography and explains how cryptographic techniques protect digital communication.

Topics covered:
- Cryptography fundamentals
- Symmetric and asymmetric encryption
- Historical ciphers
- Basic mathematical operations used in cryptography

## Task 2: Importance of Cryptography

Cryptography protects information and communication against unauthorized access and modification.

Its main purposes include:
- Confidentiality: Preventing unauthorized people from reading information.
- Integrity: Ensuring information has not been altered.
- Authenticity: Verifying the identity of a communicating party.

Cryptography is used in HTTPS connections, SSH sessions, online banking, secure file transfers, and password protection.

The Payment Card Industry Data Security Standard (PCI DSS) establishes security requirements for organizations that handle payment card information.

## Task 3: Plaintext to Ciphertext

Key terminology:

- Plaintext: The original, readable message or data.
- Ciphertext: The encrypted, unreadable representation of the original data.
- Cipher: An algorithm used to encrypt and decrypt information.
- Key: A value used by a cipher to encrypt or decrypt data.
- Encryption: The process of converting plaintext into ciphertext.
- Decryption: The process of recovering plaintext from ciphertext.

Encryption uses a cipher and an appropriate key to protect information. Decryption reverses the process using the required key.

## Task 4: Historical Ciphers

The Caesar cipher is a historical encryption technique that shifts each letter by a fixed number of positions in the alphabet.

For example, using a shift of three:

Plaintext:
```text
TRYHACKME
```

Ciphertext:
```text
WUBKDFNPH
```

To decrypt the message, each letter is shifted three positions to the left.

The Caesar cipher is insecure by modern standards because it has only 25 meaningful non-zero shifts. An attacker can test every possible key using brute force.

Other historical cryptographic systems include the Vigenere cipher, the Enigma machine, and the one-time pad.

## Task 5: Types of Encryption

### Symmetric Encryption

Symmetric encryption uses the same secret key for encryption and decryption.

Examples:
- DES (Data Encryption Standard)
- 3DES (Triple DES)
- AES (Advanced Encryption Standard)

DES uses a 56-bit key and is no longer considered secure. 3DES was introduced as an interim improvement but has also been deprecated.

AES was adopted as a standard in 2001 and supports key sizes of 128, 192, and 256 bits.

A major challenge with symmetric encryption is securely sharing the secret key between communicating parties.

### Asymmetric Encryption

Asymmetric encryption uses a pair of keys:
- Public key: Shared with others.
- Private key: Kept secret by its owner.

For confidentiality, a sender can encrypt information using the recipient's public key. The recipient then decrypts it using their private key.

Examples include RSA and elliptic curve cryptography (ECC). Diffie-Hellman is commonly used for key agreement.

Asymmetric cryptography can help establish secure communication without requiring both parties to share a secret key in advance. It is generally slower than symmetric encryption.

## Task 6: Basic Math

### XOR Operation

XOR stands for exclusive OR. It compares two binary bits and returns 1 when they differ and 0 when they are equal.

Truth table:

| A | B | A XOR B |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

Example:

```text
  1001
XOR 1010
  ----
  0011
```

XOR has useful properties:
- A XOR A = 0
- A XOR 0 = A
- A XOR B = B XOR A

Applying XOR twice with the same key restores the original value. This property makes XOR useful in cryptographic algorithms.

### Modulo Operation

The modulo operator (%) returns the remainder after integer division.

Examples:

```text
25 % 5 = 0
23 % 6 = 5
23 % 7 = 2
60 % 12 = 0
```

For the room's calculation:

```text
118613842 % 9091 = 3565
```

The modulo operation is used in many mathematical algorithms and cryptographic systems.

Python can calculate modulo operations directly:

```python
print(118613842 % 9091)
```

## Task 7: Summary

This room introduced the importance of cryptography, the distinction between plaintext and ciphertext, historical encryption methods, and the differences between symmetric and asymmetric encryption.

It also covered XOR and modulo operations, which are important mathematical building blocks in computing and cryptography.

The next room is [Public Key Cryptography Basics](https://tryhackme.com/r/room/publickeycrypto).

## Key Takeaways

- Cryptography helps protect confidentiality, integrity, and authenticity.
- Plaintext is converted into ciphertext through encryption.
- Decryption recovers the original plaintext.
- Symmetric encryption uses one shared secret key.
- Asymmetric encryption uses a public and private key pair.
- The Caesar cipher is vulnerable to brute-force attacks.
- XOR compares binary bits and can be reversed by applying the same key again.
- Modulo returns the remainder of an integer division.

