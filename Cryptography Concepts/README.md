Cryptography Concepts

TryHackMe room: Cryptography Concepts

Task 1: Introduction

Completed the introduction to cryptography and started the room.

Task 2: Hiding Information - Symmetric Encryption
Key Concepts
Plaintext is readable information.
Ciphertext is encrypted or scrambled information.
A key controls the encryption and decryption process.
An algorithm is the method used to transform the data.
Symmetric Encryption

Symmetric encryption uses the same key for encryption and decryption.

The Caesar cipher was used to demonstrate this concept.

Caesar Cipher Exercises

Caesar key 5:

CYBER → HDGJW

Decoded ciphertext:

FVZCYR PNRFNE PVCURE
→ SIMPLE CAESAR CIPHER
Secret Message Rescue

Completed all four levels:

DWWDFN WRPRUURZ with key 3
ATTACK TOMORROW
SECRET with key 5
XJHWJY
ESP DJDEPX TD LE CTDV with key 11
THE SYSTEM IS AT RISK
XLMW MW XLI JMREP GSHI with key 4
THIS IS THE FINAL CODE
Task 3: Sharing Keys Safely - Asymmetric Encryption
Asymmetric Encryption

Asymmetric encryption uses two linked keys:

Public key — can be shared with others.
Private key — must remain secret.
Questions

Which key stays secret?

Private key

Alice encrypts with Bob's public key. Can only Bob's private key decrypt it?

Yay

What problem does asymmetric encryption solve?

Key distribution

What encryption type is used for bulk data after the initial HTTPS exchange?

Symmetric encryption
HTTPS

Real-world systems commonly combine asymmetric and symmetric encryption:

Asymmetric encryption is used during the initial handshake to establish a shared key.
Symmetric encryption is then used for the actual data because it is faster and more efficient.
Task 4: Conclusion

Completed the room.

The room covered:

Plaintext and ciphertext
Encryption keys
Cryptographic algorithms
Symmetric encryption
Asymmetric encryption
Caesar cipher
Key distribution
HTTPS encryption
The relationship between asymmetric and symmetric encryption

Cryptography helps protect confidentiality and integrity, but it is only one layer of a larger security strategy. Other important layers include strong passwords, secure key storage, user awareness, software updates, monitoring, and incident response.

What I Learned
How plaintext becomes ciphertext through encryption.
The role of keys and algorithms in cryptography.
How symmetric encryption works.
Why symmetric encryption has a key distribution problem.
How asymmetric encryption uses public and private keys.
How asymmetric and symmetric encryption work together in HTTPS.
Why cryptography is an important part of cybersecurity and defensive security.
