# TryHackMe - John the Ripper: The Basics

Room: [John the Ripper: The Basics](https://tryhackme.com/room/johntheripperbasics)  
Category: Password Cracking  
Topics: John the Ripper, Hash Cracking, Wordlists, Custom Rules, Archive Passwords, SSH Keys

## Task 1 - Introduction

Introduction to John the Ripper, a password-cracking tool used to test password strength and recover passwords from supported hashes.

## Task 2 - What is John the Ripper?

John the Ripper is a password security auditing and recovery tool. Jumbo John is the most popular extended version.

## Task 3 - Wordlists

The rockyou.txt wordlist was created from the rockyou.com data breach.

## Task 4 - Cracking Basic Hashes

John can automatically detect some hash formats or use a specified format with the --format option. The --wordlist option selects a wordlist for password attempts.

Answers:

1. hash1.txt type: MD5
2. hash1.txt password: biscuit
3. hash2.txt type: SHA1
4. hash2.txt password: kangeroo
5. hash3.txt type: SHA256
6. hash3.txt password: microphone
7. hash4.txt type: Whirlpool
8. hash4.txt password: colossal

## Task 5 - Cracking Windows Authentication Hashes

Windows stores password hashes in the NT hash format, commonly associated with NTLM.

Answers:

1. Format: nt
2. Password: mushroom

## Task 6 - Cracking /etc/shadow Hashes

The unshadow utility combines passwd and shadow entries into a format John can process.

Answer:

- Root password: 1234

## Task 7 - Single Crack Mode

Single Crack mode uses account information, such as usernames and GECOS fields, to generate password candidates through word mangling.

Answer:

- Joker password: Jok3r

## Task 8 - Custom Rules

Custom rules generate password candidates by applying transformations to words. They can exploit predictable password complexity patterns.

Answers:

1. Password complexity predictability
2. Rule to append uppercase letters: Az"[A-Z]"
3. Custom rule flag: --rule=THMRules

## Task 9 - Cracking Password-Protected ZIP Files

The zip2john utility converts ZIP archive password data into a format John can process.

Answers:

1. ZIP password: pass123
2. Flag: THM{w3ll_d0n3_h4sh_r0y4l}

## Task 10 - Cracking Password-Protected RAR Files

The rar2john utility converts RAR archive password data into a format John can process.

Answers:

1. RAR password: password
2. Flag: THM{r4r_4rch1ve5_th15_t1m3}

## Task 11 - Cracking SSH Keys

The ssh2john utility converts an SSH private key into a format John can process to test its passphrase.

Answer:

- SSH private key passphrase: mango

## Task 12 - Further Reading

The room is complete. Consult the [Openwall John the Ripper documentation](https://www.openwall.com/john/) for additional usage details and advanced rules.
