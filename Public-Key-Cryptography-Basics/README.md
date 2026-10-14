# TryHackMe: Public Key Cryptography Basics

Platform: [TryHackMe](https://tryhackme.com/)  
Room: Public Key Cryptography Basics  
Category: Cryptography  
Topics: Public-Key Cryptography, RSA, Diffie-Hellman, SSH, Digital Signatures, Certificates, PGP/GPG

---

## Overview

This room introduces the fundamentals of public-key cryptography, also known as asymmetric cryptography. It covers how public and private keys are used to secure communications, how key exchange works, and how digital signatures and certificates help establish trust.

The room also introduces OpenPGP and GPG for encrypting and decrypting messages.

## Tasks Completed

### Task 1: Introduction

Introduction to public-key cryptography and its role in protecting communications and data.

### Task 2: What Is Public-Key Cryptography?

Learned the difference between public and private keys and how asymmetric cryptography enables secure communication.

### Task 3: RSA

Studied the RSA algorithm and its mathematical foundations.

Key concepts:
* Modulus: \(n = p \times q\)
* Euler's totient function: \(\varphi(n) = (p-1)(q-1)\)
* Public-key cryptography and RSA key generation

Practical exercise:
* \(p = 4391\)
* \(q = 6659\)
* \(n = 29239669\)
* \(\varphi(n) = 29228620\)

### Task 4: Diffie-Hellman Key Exchange

Learned how two parties can establish a shared secret over an insecure communication channel.

Given:
* Prime number: \(p = 29\)
* Generator: \(g = 5\)
* Alice's private value: \(a = 12\)
* Bob's private value: \(b = 17\)

Results:
* Alice's public value: \(A = 7\)
* Bob's public value: \(B = 9\)
* Shared secret: \(s = 24\)

### Task 5: SSH

Learned how SSH uses public-key authentication to provide secure remote access.

Key concepts:
* Public and private key pairs
* RSA private keys
* SSH key-based authentication
* Secure handling of private key files and file permissions

### Task 6: Digital Signatures and Certificates

Studied how digital signatures help verify authenticity and integrity, and how digital certificates establish trust between systems.

Key concepts:
* Digital signatures
* Digital certificates
* TLS certificates
* Let's Encrypt

### Task 7: PGP and GPG

Learned how OpenPGP and GPG can be used to encrypt and decrypt messages.

Practical exercises:
* Importing a public key
* Decrypting an encrypted message
* Retrieving the secret word from the decrypted content

Secret word: `Pineapple`

### Task 8: Conclusion

Reviewed the main concepts covered in the room and the differences between cryptography and cryptanalysis.

Key definitions:
* Cryptography: The science of protecting information and communications.
* Cryptanalysis: The study of methods used to break or bypass cryptographic systems.
* Brute-force attack: An attack that tries every possible password or key.
* Dictionary attack: An attack that tests likely passwords from a predefined list.

The room concludes by introducing hashing as the next topic to study.

## Key Takeaways

* Public-key cryptography uses mathematically related public and private keys.
* RSA is an asymmetric cryptographic algorithm based on number theory.
* Diffie-Hellman enables two parties to establish a shared secret.
* SSH supports secure remote access and public-key authentication.
* Digital signatures help verify data integrity and authenticity.
* Digital certificates help establish trust in public keys.
* GPG supports encryption and decryption using OpenPGP.
* Brute-force and dictionary attacks are different approaches to guessing passwords or keys.

## Conclusion

This room provided a practical introduction to public-key cryptography, including RSA, Diffie-Hellman, SSH key pairs, digital signatures, certificates, and OpenPGP/GPG.

These concepts form an important foundation for further studies in cybersecurity, network security, and cryptography.

---

This write-up is for educational purposes and documents the concepts and exercises covered in the TryHackMe room.
