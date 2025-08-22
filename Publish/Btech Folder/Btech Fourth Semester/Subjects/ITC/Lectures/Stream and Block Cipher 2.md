---
Title: Introduction to Cryptography Lecture 6
Status: 
marker: 
tags: 
Date: 2025.01.20
Time: 09:12
---
Continued from [[Transposition Cipher]]

# Stream And Block Cipher
The cipher methods are divided mainly into two parts  block cipher and stream cipher.

---
### Stream Ciphers

- A **stream cipher** encrypts data one bit or byte at a time, using a key stream that is typically generated based on the secret key.
- If the key stream repeats itself, the cipher is considered **periodic**. An example of this is the **Vigenère Cipher**.
    - **Vigenère Cipher:** The key is repeated if it is shorter than the message. It encrypts each character of the message using the corresponding character of the key. This makes it a periodic cipher.
- In contrast, the **one-time pad** is a stream cipher, but it is **not periodic** because its key stream never repeats. This makes the one-time pad theoretically unbreakable if the key is truly random, used only once, and is as long as the message.
- We have already studied this in [[Vigenère's and Playfair Cipher]].

---

## Block Cipher
 A block cipher is an encryption algorithm that takes a fixed-size input (e.g., b bits) and produces a ciphertext of b bits. If the input is larger than b bits, it can be divided further.
1. **Concept of Block Cipher:**
   - Some ciphers divide a message into fixed-size parts (blocks) and encrypt each block using the same key.
2. **Definition:**
   - Let $E$ represent an encryption algorithm, and $E_k(b)$ be the encryption of message $b$ using key $k$.
3. **Mathematical Representation:**
   - If a message $m$ consists of parts $b_1, b_2, \dots$, where each $b_i$ is of a fixed length, then a block cipher encrypts each block independently as follows:
$$E_k(m) = E_k(b_1)E_k(b_2) \dots$$
1. **Example of Block Cipher:**
   - DES (Data Encryption Standard) is a block cipher that divides the message into 64-bit blocks and encrypts each block using a 56-bit key.

![[IMG-20250730000529043.png|center|300]]

- **Block ciphers** encrypt and decrypt **multiple bits** at once, rather than processing one bit at a time, making them more efficient for encrypting larger datasets.
- **Performance:** Software implementations of block ciphers tend to **run faster** compared to stream ciphers, which encrypt data bit-by-bit.
- **Error Handling:** Errors in transmitting one block typically do not affect other blocks. Since each block is encrypted independently using the same key, **identical plaintext blocks** will produce **identical ciphertext blocks**.
- **Analysis:** This property allows an analyst to search for specific data by analyzing the encryption of a known plaintext block.

---
## Disadvantages of Block Cipher

1. **Example of Block Cipher with Banking Data:**
    
    - **Data Example:**
        - MEMBER: HOLLY INCOME $100,000
        - MEMBER: HEIDI INCOME $100,000
    - The encrypted result (ciphertext) of these records under a block cipher is:
        
        ```
        ABCQZRME GHQMRSIB CTXUVYSS RMGRPFQN
        ABCQZRME ORMPABRZ CTXUVYSS RMGRPFQN
        ```
        
    - **Risk:** If an attacker knows that "CTXUVYSS" is the encryption of the "INCOME" keyword, they can deduce that Holly and Heidi have the same income, which poses a security risk.
    - **Solution:** To prevent this type of attack, additional information such as a **sequence number** or some information from the previous ciphertext block can be inserted into the plaintext before encryption. This disrupts patterns in the ciphertext. However, the downside is that this reduces the effective block size.
2. **Block Cipher vs. Stream Cipher:**
    

|Feature|**Block Cipher**|**Stream Cipher**|
|---|---|---|
|**Data Processing**|Encrypts fixed-size blocks (e.g., 64 or 128 bits)|Encrypts data one bit or byte at a time|
|**Encryption Mode**|Operates on a block-by-block basis|Operates continuously or on small chunks of data|
|**Complexity**|More complex due to block handling, padding, and modes of operation|Simpler to implement due to continuous processing|
|**Padding Requirement**|Requires padding if the plaintext size is not a multiple of the block size|No padding required as data is processed bit-by-bit or byte-by-byte|
|**Error Propagation**|Errors in one block may affect subsequent blocks (e.g., CBC mode)|Errors are localized to a single bit/byte and do not propagate|
|**Initialization Vector (IV)**|Often requires an IV for modes like CBC or GCM|Often requires an IV or key stream initialization|
|**Security**|Stronger against certain attacks due to structured encryption|More vulnerable to attacks like key reuse in RC4|
|**Examples**|AES, DES, Triple DES, Blowfish|RSA, RC4, Salsa20, ChaCha20|
|**Memory Requirements**|Block ciphers consume more memory due to fixed-size blocks|Stream ciphers use less memory as they process data bit-by-bit|
|**Use Cases**|File encryption, database encryption, and storage encryption|Real-time communications, video streaming, and VoIP encryption|
|**Performance**|Better for larger chunks of data|Faster for real-time or streaming data encryption|

---
# Cryptanalysis

1. **Brute Force Attack:**
    
    - Tries all possible keys to decrypt the ciphertext.
    - **Effective** only for block ciphers with small key spaces.

2. **Differential Cryptanalysis:**
    
    - Analyzes plaintext pairs' differences and their effect on ciphertext.
    - **Example:** Applied to DES, revealing design insights.

3. **Linear Cryptanalysis:**
    
    - Uses linear approximations to find correlations between plaintext, ciphertext, and the key.
    - **Effective** against DES and older block ciphers.

4. **Side-Channel Attacks:**
    
    - Exploits physical information leaks (e.g., timing, power consumption, electromagnetic emissions).
    - **Example:** Timing attacks on AES implementations can recover secret keys.

5. **Padding Oracle Attack:**
    
    - Exploits improper error handling in cipher modes like CBC when padding is used.
    - **Example:** Attacker manipulates ciphertext to decrypt data without knowing the key.

6. **Meet-in-the-Middle Attack:**
    
    - Targets ciphers with multiple encryption layers (e.g., 3DES).
    - Reduces effective key size by simultaneously working on both encryption and decryption.

---

## **Electronic Code Book (ECB)**
Electronic code block takes a message input as $P_n$ and then encrypt using a key $K$ and the ciphered text $C_n$ comes out as the output
#### Advantages
- Parallel encryption of blocks of bits is possible, thus it is a faster way of encryption.
#### Disadvantages
- Prone to cryptanalysis since there is a direct relationship between plaintext and ciphertext.
- Identical plaintext blocks produce identical ciphertext blocks, which can reveal patterns.

## Chaining of ECB's
In an ECB we can add an additional step where we use an initializing vector $IV$ to perform XOR on the message $P1$ and then use the $key$ ($K$) to encrypt it and get the ciphered text. This way there's a dependency created b/w the previous blocks.

```
IV
 |
 XOR
  | \
  P1 --> Encrypt --> C1
          |
          |
         XOR
          | \
         P2 --> Encrypt --> C2
                |
                |
               XOR
                | \
               P3 --> Encrypt --> C3
                     ...

```

#### Advantages
- More secure than ECB as it hides patterns.
- Better resistive nature towards cryptanalysis than ECB.







###### Information
- date: 2025.01.20
- time: 09:12
- Continued to [[Introduction to Cryptography Lecture 7]]
