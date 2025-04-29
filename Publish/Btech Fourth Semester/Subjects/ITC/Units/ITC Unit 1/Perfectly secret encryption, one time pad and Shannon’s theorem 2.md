---
Title: Perfectly secret encryption, one time pad and Shannon’s theorem
Status: true
marker:
  - "[[Cryptography]]"
  - "[[ITC Unit 1]]"
tags:
  - BTech
  - Note
Date: 2025.04.19
Time: 11:52
---
# Perfectly Secret Encryption
> [!Related Notes]
> - [[Introduction, Security goals (CIA triad)]]
> - [[Goals of cryptography, principles of modern cryptography]]
> - [[Perfectly secret encryption, one time pad and Shannon’s theorem]]
> - [[Cryptographic applications]]


Perfect secrecy is a concept in cryptography that describes an encryption system that cannot be broken even with unlimited computational resources. A perfectly secret encryption system has the following characteristics:

1. **Unbreakable**
    - Theoretically impossible to decrypt without the key
2. **Random Key**
    - Key must be as long as the message
3. **One-Time Use**
    - Each key can only be used once

These principles are embodied in the [[Perfectly secret encryption, one time pad and Shannon's theorem\#One-Time Pad|One-Time Pad]] and formalized in [[Perfectly secret encryption, one time pad and Shannon's theorem\#Shannon's Theorem|Shannon's Theorem]].

## One-Time Pad

The One-Time Pad (also known as the Vernam Cipher) is a cryptographic technique where a random key is used to encrypt a message, ensuring perfect secrecy. This method is provably unbreakable if the key is truly random and used only once.

### Example of One-Time Pad / Vernam Cipher

```
Message: HELLO
Key:     XMCKL

For Encryption:
Message:         H  E  L  L  O
                 7  4  11 11 14
Key:             X  M  C  K  L
                 23 12 2  10 11
Message + Key:   30 16 13 21 25
(Message + Key) mod 26: 4  16 13 21 25
Ciphertext:      E  Q  N  V  Z

For Decryption:
Ciphertext:      E  Q  N  V  Z
                 4  16 13 21 25
Key:             X  M  C  K  L
                 23 12 2  10 11
Message = (Ciphertext - Key + 26) mod 26
                 7  4  11 11 14
Message:         H  E  L  L  O
```

The encryption formula uses the XOR operation: C = M ⊕ K
To decrypt: M = C ⊕ K

## Shannon's Theorem

Claude Shannon's mathematical proof establishes that perfectly secret encryption is achievable only if the key is at least as long as the message and used only once. This theorem establishes the theoretical foundation for secure cryptography.

### Proof of Perfect Secrecy

For any message M, the ciphertext C depends entirely on the key K.
K is a random variable with a uniform distribution.
For any given C, multiple values of M are equally likely because the key K is random.

Thus: P(M|C) = P(M)

This implies that the ciphertext C provides no additional information about the plaintext message M.

### Shannon's Theorem Analysis Example

**Problem**: A secure cipher requires that the ciphertext provide no information about the plaintext without the key. Assume you are encrypting a 4-character plaintext with an alphabet of 26 letters (English alphabet) using a one-time pad. Each key is randomly selected and is as long as the plaintext.

**Steps to Analyze Using Shannon's Principles**:

1. **Plaintext Entropy**:
    - Number of possible plaintexts, P = 26^4 = 456,976
    - Entropy is: H(P) = log₂(P) = log₂(456,976) ≈ 18.8 bits
2. **Key Entropy**:
    - A one-time pad requires the key to be as long as the plaintext
    - Each character in the key can be any of the 26 letters
    - Key space, K = 26^4 = 456,976
    - Entropy of the key is: H(K) = log₂(456,976) ≈ 18.8 bits
3. **Ciphertext Analysis**:
    - For a one-time pad: Ciphertext C = Plaintext P ⊕ Key K
    - The ciphertext is uniformly distributed and reveals no information about the plaintext without the key
    - Since K has the same entropy as P, the system achieves perfect secrecy
4. **Verification of Perfect Secrecy**:
    - Perfect secrecy means: H(P|C) = H(P)
    - The conditional entropy of the plaintext given the ciphertext equals the entropy of the plaintext
    - In this example, C provides no information about P without K

The one-time pad satisfies Shannon's theorem because:

- The key is as random as the plaintext
- The key space is large enough to encompass all possible plaintexts
- Without the key, the ciphertext reveals no information about the plaintext

This ensures perfect secrecy in cryptographic systems adhering to Shannon's principles.



###### Information
- date: 2025.04.19
- time: 11:52