---
Title: Shift Ciphers, Affine Ciphers
Status: 
marker:
  - "[[Introduction To Cryptography (ITC)]]"
  - "[[ITC Unit 2]]"
tags:
  - BTech
  - Note
Date: 2025.04.19
Time: 12:01
---
# Shift Ciphers, Affine Ciphers

> [!Related Notes]
>
> - [[Introduction, Security goals (CIA triad)]]
> - [[Substitution Ciphers, Transposition Ciphers]]
> - [[Stream and block ciphers, Cryptanalysis]]

## Shift Cipher

A shift cipher is one of the simplest forms of encryption, where each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet. This type of cipher is also known as a Caesar cipher when the shift value is 3, as it was reportedly used by Julius Caesar to communicate with his generals.

### Types of Shift Ciphers

- **Caesar Cipher**: Shift by k = 3
- **Negative Shift Cipher**: Shift by k = -2 (shifting backwards in the alphabet)
- **Shift Cipher with Wraparound**: Shift by k = 5 (wrapping around to the beginning of the alphabet when reaching the end)
- **ROT13**: Shift by k = 13 (exactly half the English alphabet, making encryption and decryption the same operation)
- **Shift Cipher with Numbers and Symbols**: Extends beyond just letters to include numbers and special characters


### Mathematical Representation

For a shift cipher with key k, the encryption function is:

$E(x) = (x + k) \mod 26$

where x is the numerical value of the plaintext letter (A=0, B=1, ..., Z=25).

The corresponding decryption function is:

$D(y) = (y - k) \mod 26$

where y is the numerical value of the ciphertext letter.

## Affine Cipher

The Affine cipher is a type of monoalphabetic substitution cipher that combines multiplication and addition in its encryption process. It's a generalization of the shift cipher, offering more complexity and security.

### Definition

The Affine cipher is defined by the encryption function:

$E(x) = (ax + b) \mod m$

where:

- m is the size of the alphabet (26 for English)
- a and b are the keys of the cipher
- a must be chosen such that a and m are coprime (their greatest common divisor is 1)


### Decryption

The decryption function is:

$D(y) = a^{-1}(y - b) \mod m$

where $a^{-1}$ is the modular multiplicative inverse of a modulo m, satisfying the equation:

$1 = a \cdot a^{-1} \mod m$

### Finding the Multiplicative Inverse

To find the multiplicative inverse $a^{-1}$:

1. Search each number from 1 to 25
2. Find the value that satisfies $a \cdot x \equiv 1 \pmod{26}$
3. That value x is the inverse of a

### Example of Affine Cipher Encryption

For key values a=17 and b=20, the encryption process would be:

| Original Text | ax + b (mod 26) | Encrypted Text |
| :-- | :-- | :-- |
| T (19) | 17×19+20 = 343 (mod 26) = 5 | F |
| W (22) | 17×22+20 = 394 (mod 26) = 4 | E |
| E (4) | 17×4+20 = 88 (mod 26) = 10 | K |
| N (13) | 17×13+20 = 241 (mod 26) = 7 | H |

### Example of Affine Cipher Decryption

Using $a^{-1} = 23$ (the multiplicative inverse of 17 modulo 26):


| Encrypted Text | Encrypted Value | 23×(y-b) mod 26 | Original Text |
| :-- | :-- | :-- | :-- |
| F (5) | 23×(5-20) = 23×(-15) = -345 (mod 26) = 19 | T |  |
| E (4) | 23×(4-20) = 23×(-16) = -368 (mod 26) = 22 | W |  |
| K (10) | 23×(10-20) = 23×(-10) = -230 (mod 26) = 4 | E |  |
| H (7) | 23×(7-20) = 23×(-13) = -299 (mod 26) = 13 | N |  |

### Special Cases of Affine Cipher

1. **Shift Cipher**: When a = 1, the Affine cipher reduces to a shift cipher with shift value b.
$E(x) = (1 \cdot x + b) \mod 26 = (x + b) \mod 26$
2. **Atbash Cipher**: When a = 25 (equivalent to -1 mod 26) and b = 25, the Affine cipher becomes the Atbash cipher, which maps each letter to its mirror image in the alphabet (A↔Z, B↔Y, etc.).

### Valid Keys for Affine Cipher

For the English alphabet (m = 26), a valid key requires that a and 26 are coprime. The valid values for a are: 1, 3, 5, 7, 9, 11, 15, 17, 19, 21, 23, 25.

Since there are 12 valid choices for a and 26 valid choices for b, there are a total of 12 × 26 = 312 possible valid Affine ciphers.

## Relationship Between Shift and Affine Ciphers

Shift ciphers are a particular type of Affine cipher where a = 1. This means that in a [[#Shift Cipher|Shift Cipher]], letters are only shifted by a constant value (b), while in the general Affine cipher, letters undergo both multiplication (by a) and addition (of b).

This relationship demonstrates how cryptographic techniques evolved, with each new cipher building upon and extending previous ones to provide greater security.

## Security Considerations

Both shift and Affine ciphers are vulnerable to frequency analysis attacks because they preserve the frequency distribution of letters in the plaintext. For example, in English, 'E' is the most common letter, so the most frequent letter in the ciphertext likely corresponds to 'E'.

Additionally:

- Shift ciphers have only 25 possible keys, making them vulnerable to brute force attacks.
- Affine ciphers have 312 possible keys, providing somewhat better security but still vulnerable to statistical attacks.

These classical ciphers laid the groundwork for modern [[Substitution Ciphers, Transposition Ciphers|substitution and transposition techniques]] and eventually led to the development of more secure [[Stream and block ciphers, Cryptanalysis|stream and block ciphers]].





# References


###### Information
- date: 2025.04.19
- time: 12:01