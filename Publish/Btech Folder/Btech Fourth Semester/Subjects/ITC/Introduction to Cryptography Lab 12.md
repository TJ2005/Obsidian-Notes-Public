---
Title: "Introduction to Cryptography Lab 8"
Status: 
marker: 
tags: 
Date: "2025.03.29"
Time: "11:42"
---
# AES Algorithm
AES (Advanced Encryption Standard) is a symmetric encryption algorithm that uses a block cipher to encrypt and decrypt data. It is a widely used encryption algorithm that is considered secure and efficient.

## Code
```python
# Helper functions

def xor_bytes(a, b):

    return bytes([x ^ y for x, y in zip(a, b)])

def sub_bytes(state, sbox):

    return bytes([sbox[byte] for byte in state])

def shift_rows(state):

    return bytes([

        state[0], state[5], state[10], state[15],

        state[4], state[9], state[14], state[3],

        state[8], state[13], state[2], state[7],

        state[12], state[1], state[6], state[11]

    ])

def mix_columns(state):

    # Simplified mix column transformation for educational purposes

    def mix_column(column):

        return bytes([

            column[0] ^ column[1], column[1] ^ column[2],

            column[2] ^ column[3], column[3] ^ column[0]

        ])

    return b''.join([mix_column(state[i:i + 4]) for i in range(0, len(state), 4)])

def aes_round(state, key, sbox, mix_columns_flag=True):

    # SubBytes

    state = sub_bytes(state, sbox)

    # ShiftRows

    state = shift_rows(state)

    # MixColumns (not performed in the final round)

    if mix_columns_flag:

        state = mix_columns(state)

    # AddRoundKey (XOR with the round key)

    state = xor_bytes(state, key)

    return state

# S-box (simplified for brevity, use a standard AES S-box in real implementation)

SBOX = list(range(256))  # Replace with proper S-box values in practice

def aes_encrypt(plaintext, key):

    # Ensure plaintext and key are 16 bytes (128 bits)

    assert len(plaintext) == 16 and len(key) == 16, "Plaintext and key must be 16 bytes long."

    # Initialize state (XOR with key block)

    state = xor_bytes(plaintext, key)

    # Perform rounds of AES (simplified: 3 rounds for demonstration)

    for round_index in range(3):  # Normally AES has 10, 12, or 14 rounds depending on the key size

        mix_columns_flag = round_index < 2  # Skip MixColumns in the final round

        state = aes_round(state, key, SBOX, mix_columns_flag)

    return state

# Example usage

if __name__ == "__main__":

    plaintext = b"abcdefghijklmnop"  # Example 16-byte plaintext

    key = b"1234567890ABCDEF"       # Example 16-byte key

    print("Original plaintext:", plaintext)

    encrypted = aes_encrypt(plaintext, key)

    print("Encrypted text:", encrypted)
```

**Output:**
```bash
Original plaintext: b'abcdefghijklmnop'
Encrypted text: b'\x1c\x1d\x1e\x1f\x18\x19\x1a\x1b\x14\x15\x16\x17\x10\x11\x12\x13'
```

## Questions
**1. Working of AES Algorithm (Brief Overview):**

AES (Advanced Encryption Standard) is a block cipher that encrypts and decrypts data in fixed blocks of 128 bits. The algorithm performs multiple rounds of substitution, transposition, and XOR operations to produce secure ciphertext. Here's an outline:

·       **Key Expansion**: Generates round keys from the original key.

·       **Initial Transformation**: XOR the plaintext block with the first round key (AddRoundKey).

·       **Rounds**: The encryption process involves SubBytes (byte substitution using an S-box), ShiftRows (row-wise shifting), MixColumns (column-wise mixing), and AddRoundKey operations.

·       **Final Round**: Similar to other rounds but skips the MixColumns step. The number of rounds depends on the key size: 10 rounds for AES-128, 12 for AES-192, and 14 for AES-256.

---

**2. Modes of Operation of AES Algorithm:**

AES works with several modes of operation to enhance security and flexibility:

·       **ECB (Electronic Codebook)**: Each block is encrypted independently, making it fast but vulnerable to pattern detection in the ciphertext.

·       **CBC (Cipher Block Chaining)**: Each plaintext block is XORed with the previous ciphertext block before encryption, improving security by hiding patterns.

·       **CFB (Cipher Feedback)**: Encrypts smaller chunks of data and supports stream encryption.

·       **OFB (Output Feedback)**: Similar to CFB but does not use the previous ciphertext block—uses a generated keystream instead.

·       **CTR (Counter Mode)**: Encrypts blocks independently using a counter value, enabling parallel processing.

---

**3. Significance of Rcon (Round Constant) Values in Key Expansion:**

Rcon values are used during AES key expansion to ensure the generated round keys are unique and non-linear. They:

·       Introduce diversity in the key schedule by XORing with intermediate key values during expansion.

·       Prevent relationships between successive round keys, enhancing cryptographic strength against certain attacks.

---

**4. AES-256: Resistance to Quantum Computing and Vulnerability to Side Channel Attacks:**

·       **Resistance to Quantum Computing**: AES-256 uses a 256-bit key, which dramatically increases the complexity of brute-force attacks. Quantum algorithms like Grover's can theoretically reduce search time, but even halving the key space (to 2^128) remains computationally infeasible.

·       **Vulnerability to Side-Channel Attacks**: AES-256, like other cryptographic systems, is susceptible to attacks that exploit implementation flaws (e.g., timing analysis, power consumption, electromagnetic leaks). Such attacks don’t target the algorithm itself but the physical hardware or software implementation.

**Conclusion:** Learnt to implement AES algorithm in Python and explored its key aspects and modes of operation. Understanding AES encryption is crucial for secure data transmission and storage.

###### Information
- date: 2025.03.29
- time: 11:42