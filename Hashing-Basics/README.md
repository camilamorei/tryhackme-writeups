# TryHackMe: Hashing Basics

Room: [Hashing Basics](https://tryhackme.com/room/hashingbasics)  
Category: Cryptography  
Topics: Hashing, Hash Functions, Rainbow Tables, Password Cracking, Hashcat, Encoding, HMAC

## Task 1: Introduction

Introduction to hashing and its role in cryptography and password security.

## Task 2: Hashing

This task covers the basic properties of hash functions and common hashing algorithms.

Answers:

1. SHA256 hash of `passport.jpg`: `77148c6f605a8df855f2b764bcc3be749d7db814f5f79134d2aa539a64b61f02`
2. MD5 output size: `16` bytes
3. Number of possible outputs for an 8-bit hash: `256`

## Task 3: Passwords and Wordlists

This task introduces password wordlists and their use in password recovery.

Answers:

1. 20th password in `rockyou.txt`: `qwerty`

## Task 4: Recognising Password Hashes

This task explores identifying password hashes and understanding rainbow tables.

Answers:

1. Hash `4c5923b6a6fac7b7355f53bfe2b8f8c1`: `inS3CyourP4$$`
2. Hash `5b31f93c09ad1d065c0491b764d04933`: `tryhackme`
3. Should passwords be encrypted instead of hashed for verification? `Nay`

## Task 5: Password Cracking

This task introduces password hash formats and Hashcat modes.

Answers:

1. yescrypt hash size: `256`
2. Hashcat mode for Cisco-ASA MD5: `2410`
3. Cisco-IOS hash prefix `$9$`: `scrypt`

## Task 6: Password Cracking with Hashcat

This task covers cracking password hashes using Hashcat.

Answers:

1. bcrypt hash: `85208520`
2. SHA2-256 hash: `halloween`
3. sha512crypt hash: `spaceman`
4. MD5 hash: `funforyou`

Relevant Hashcat modes:

- bcrypt: `3200`
- SHA2-256: `1400`
- sha512crypt: `1800`

Example command to display recovered passwords:

```bash
hashcat --show hashes.txt
```

The hash file and mode must match the format being tested.

## Task 7: HMAC and File Integrity

This task covers HMAC and the use of hashes to verify file integrity.

Answers:

1. SHA256 hash of `libgcrypt-1.11.0.tar.bz2`: `09120c9867ce7f2081d6aaa1775386b98c2f2f246135761aae47d81f58685b9c`
2. Hashcat mode for HMAC-SHA512 with the password as the key: `1750`

To calculate a file's SHA256 hash:

```bash
sha256sum ~/Hashing-Basics/Task-7/libgcrypt-1.11.0.tar.bz2
```

## Task 8: Conclusion

This task reviews the differences between hashing, encoding, and encryption.

Answer:

1. Base64 decoding of `RU5jb2RlREVjb2RlCg==`: `ENcodeDEcode`

To decode a Base64 file in the terminal:

```bash
base64 -d decode-this.txt
```

## Key Takeaways

- Hashing produces a fixed-size digest from input data.
- Hash functions are used to verify data integrity and support password storage.
- Rainbow tables and wordlists can help recover weak passwords.
- Hashcat supports multiple hash formats through different modes.
- HMAC combines a cryptographic hash function with a secret key.
- Encoding, hashing, and encryption serve different purposes.

## Tools Used

- Linux terminal
- `sha256sum`
- `base64`
- Hashcat
- `rockyou.txt`

## Disclaimer

This writeup is for educational purposes and documents my progress through the TryHackMe Hashing Basics room. Perform password recovery and security testing only on systems and data you are authorized to use.
