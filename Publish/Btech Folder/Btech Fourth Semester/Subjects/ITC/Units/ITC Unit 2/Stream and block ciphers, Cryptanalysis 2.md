---
Title: Stream and block ciphers, Cryptanalysis
Status: 
marker:
  - "[[ITC Unit 2]]"
  - "[[Introduction To CryptoGraphy]]"
tags:
  - BTech
  - Note
Date: 2025.04.19
Time: 12:35
---
	# Stream and block ciphers, Cryptanalysis

> [!Related Notes]
>
> - [[Shift Ciphers, Affine Ciphers]]
> - [[Substitution Ciphers, Transposition Ciphers]]
> - [[Perfectly secret encryption, one time pad and Shannon's theorem]]

## Stream Ciphers

Stream ciphers encrypt data one bit or byte at a time, making them well-suited for applications where data size is unknown beforehand or arrives in a continuous stream.

### Characteristics of Stream Ciphers

- Process data bit-by-bit or byte-by-byte
- Maintain a secret "state" that evolves during encryption
- Generate a pseudorandom keystream that is combined with plaintext
- Typically use XOR operation to combine keystream with plaintext


### Stream Cipher Operation

The basic operation of a stream cipher can be represented as:

$C_i = P_i \oplus K_i$

For decryption:

$P_i = C_i \oplus K_i$

Where:

- $C_i$ is the ith ciphertext bit/byte
- $P_i$ is the ith plaintext bit/byte
- $K_i$ is the ith keystream bit/byte
- $\oplus$ represents the XOR operation


### Stream Cipher Example

```
Plaintext:  10011001
Keystream:  11000011
-----------------
Ciphertext: 01011010 (XOR result)
```


### Types of Stream Ciphers

1. **Synchronous Stream Ciphers**
    - Keystream generation is independent of plaintext and ciphertext
    - Sender and receiver must be synchronized
    - Errors affect only the corresponding bit/byte
2. **Self-Synchronizing Stream Ciphers**
    - Keystream depends on previous ciphertext bits
    - Can recover from synchronization loss after receiving enough ciphertext
    - Errors propagate for a limited number of bits
3. **One-Time Pad**
    - Uses a truly random keystream the same length as the message
    - Keystream used only once
    - Theoretically unbreakable if implemented correctly
    - Related to [[Perfectly secret encryption, one time pad and Shannon's theorem|Shannon's theorem]]

### Advantages of Stream Ciphers

- Fast and efficient implementation
- Low hardware complexity
- Minimal error propagation
- Suitable for real-time applications
- No padding required


### Disadvantages of Stream Ciphers

- Vulnerable to key reuse attacks
- Often lack integrity protection
- Synchronization issues in some implementations
- Can be vulnerable if keystream generation is weak


## Block Ciphers

Block ciphers encrypt fixed-size blocks of data at once, typically 64 or 128 bits, using the same key for each block.

### Characteristics of Block Ciphers

- Process data in fixed-size blocks
- Apply complex transformations to each block
- Use the same key for all blocks
- Employ various modes of operation to handle messages longer than one block


### Block Cipher Structure

A typical r-round block cipher structure:

1. Divide plaintext into fixed-size blocks
2. For each block:
    - Apply initial transformation
    - Perform r rounds of substitution and permutation operations
    - Apply final transformation
3. Combine the encrypted blocks to form the ciphertext

### Substitution-Permutation Network (SPN)

Many block ciphers use an SPN structure:

1. Key mixing: XOR the block with a round key
2. Substitution: Pass the result through S-boxes (substitution boxes)
3. Permutation: Rearrange the bits according to a fixed pattern
4. Repeat for multiple rounds

### Block Cipher Modes of Operation

1. **Electronic Codebook (ECB)**
    - Each block encrypted independently
    - Same plaintext block produces same ciphertext block
    - Vulnerable to pattern analysis
2. **Cipher Block Chaining (CBC)**
    - Each block XORed with previous ciphertext block before encryption
    - Requires initialization vector (IV) for first block
    - Error in one block affects all subsequent blocks
3. **Counter Mode (CTR)**
    - Converts block cipher into stream cipher
    - Encrypts counter values and XORs with plaintext
    - Allows parallel encryption/decryption
4. **Cipher Feedback (CFB) and Output Feedback (OFB)**
    - Turn block ciphers into self-synchronizing stream ciphers
    - Used for stream-oriented applications

### Advantages of Block Ciphers

- Strong diffusion and confusion properties
- Well-studied security properties
- Versatile through different modes of operation
- Suitable for encrypting structured data


### Disadvantages of Block Ciphers

- Requires padding for messages not a multiple of block size
- Generally slower than stream ciphers
- Some modes vulnerable to specific attacks
- Error propagation in certain modes


## Comparison of Stream and Block Ciphers

| Feature | Stream Cipher | Block Cipher |
| :-- | :-- | :-- |
| Data Processing | One bit/byte at a time | Fixed-size blocks |
| Encryption Mode | Continuous | Block-by-block |
| Complexity | Simpler implementation | More complex due to block handling |
| Padding | No padding required | Requires padding for incomplete blocks |
| Error Propagation | Errors localized to single bit/byte | May affect multiple blocks (depending on mode) |
| Initialization Vector | Often requires IV | Depends on mode of operation |
| Security | Vulnerable to key reuse attacks | Stronger against certain attacks |
| Examples | RC4, Salsa20, ChaCha20 | AES, DES, Triple DES, Blowfish |
| Memory Requirements | Lower memory requirements | Higher memory requirements |
| Use Cases | Real-time communications, streaming | File encryption, database encryption |
| Performance | Faster for real-time data | Better for larger chunks of data |

## Cryptanalysis

Cryptanalysis is the study of analyzing and breaking cryptographic systems. It plays a crucial role in evaluating the security of ciphers.

### General Approaches to Cryptanalysis

1. **Brute Force Attack**
    - Try all possible keys until the correct one is found
    - Effectiveness depends on key space size
    - Computationally intensive but guaranteed to work eventually
2. **Frequency Analysis**
    - Exploits the non-uniform distribution of letters in natural languages
    - Effective against simple [[Substitution Ciphers, Transposition Ciphers|substitution ciphers]]
    - Less effective against polyalphabetic and modern ciphers
3. **Pattern Recognition**
    - Looks for patterns or structures in the ciphertext
    - Effective against some [[Substitution Ciphers, Transposition Ciphers|transposition ciphers]]
4. **Known/Chosen Plaintext Attacks**
    - Analyzes pairs of known plaintext and corresponding ciphertext
    - Attempts to deduce the key or algorithm properties

### Cryptanalysis of Stream Ciphers

1. **Key Reuse Attack**
    - If the same key/keystream is reused, XORing two ciphertexts eliminates the key
    - Results in XOR of two plaintexts, which can be analyzed
    - Example: $C_1 \oplus C_2 = (P_1 \oplus K) \oplus (P_2 \oplus K) = P_1 \oplus P_2$
2. **Weak Key Stream Generation**
    - If the pseudorandom generator has detectable patterns
    - Example: RC4 cipher has known biases in its output
3. **Chosen Plaintext Attack (CPA)**
    - If attacker can control part of the plaintext
    - Can deduce information about the keystream
4. **Bit-Flipping Attack**
    - Flipping bits in ciphertext causes predictable changes in plaintext
    - Can lead to data corruption or malicious behavior

### Cryptanalysis of Block Ciphers

1. **Differential Cryptanalysis**
    - Analyzes how specific differences in plaintext pairs affect the resulting ciphertext differences
    - Used to reveal insights about the cipher's internal structure
2. **Linear Cryptanalysis**
    - Uses linear approximations to find correlations between plaintext, ciphertext, and key bits
    - Effective against DES and other older block ciphers
3. **Side-Channel Attacks**
    - Exploits information leaks through timing, power consumption, or electromagnetic emissions
    - Can recover keys without breaking the mathematical security
4. **Padding Oracle Attack**
    - Exploits improper error handling in block cipher modes that use padding
    - Can decrypt data without knowing the key
5. **Meet-in-the-Middle Attack**
    - Targets ciphers with multiple encryption layers
    - Reduces the effective key size by working from both ends simultaneously

## Relationship to Classical Ciphers

Modern stream and block ciphers evolved from classical [[Substitution Ciphers, Transposition Ciphers|substitution and transposition ciphers]]:

- Stream ciphers can be viewed as sophisticated versions of the [[The Vigenere Cipher, Playfair Ciphers|Vigenère cipher]]
- Block ciphers often combine substitution and transposition principles in complex ways
- The [[Perfectly secret encryption, one time pad and Shannon's theorem|one-time pad]] is a theoretical ideal that stream ciphers attempt to approximate

Understanding the strengths and weaknesses of classical ciphers provides valuable insights into the design principles of modern cryptographic algorithms and the evolution of cryptanalytic techniques.

<div style="text-align: center">⁂</div>
###### Information
- date: 2025.04.19
- time: 12:35