---
Title: Modern Block Cipher and its components(D- Boxes and S-Boxes)
Status: 
marker:
  - "[[ITC Unit 3]]"
tags:
  - BTech
  - Note
Date: 2025.05.05
Time: 07:19
---
# Modern Block Cipher and its Components (D-Boxes and S-Boxes)

A block cipher is a deterministic algorithm that operates on fixed-length groups of bits called blocks. It encrypts an m-bit block of plaintext and decrypts an m-bit block of ciphertext, using the same k-bit key for both operations[4][7]. Unlike stream ciphers that encrypt one bit at a time, block ciphers process entire blocks simultaneously.

In a block cipher:
- Plaintext is divided into fixed-size blocks (typically 64 or 128 bits)
- Each block is encrypted independently using the same key
- The encryption function must be invertible (one-to-one) to allow decryption[6]

## Modern Block Cipher Examples
Modern block ciphers include:

**DES (Data Encryption Standard)**:
- Uses 64-bit blocks and a 56-bit key
- Based on the Feistel cipher structure
- Consists of 16 rounds of processing[4]

**AES (Advanced Encryption Standard)**:
- Uses 128-bit blocks and key sizes of 128, 192, or 256 bits
- Not based on Feistel structure
- Consists of 10, 12, or 14 rounds depending on key size[4]

**IDEA (International Data Encryption Algorithm)**:
- Operates on 64-bit blocks using a 128-bit key
- Uses eight identical transformation rounds and a half-round output transformation
- Combines operations from different algebraic groups[7]

## Substitution and Transposition
Modern block ciphers typically combine two fundamental techniques:
**Substitution**: Replaces each character with a different character, integer, or symbol, changing the identity while maintaining position[2][5].
**Transposition**: Rearranges the position of characters without changing their identity[2].

The combination of substitution and transposition operations creates confusion and diffusion:
- **Confusion**: Obscures the relationship between the key and ciphertext
- **Diffusion**: Spreads the influence of each plaintext bit over many ciphertext bits

## Components of Modern Block Ciphers

### D-Boxes (Permutation Boxes)

D-boxes perform transposition operations, rearranging bits according to specific patterns[1][5]. There are three types:
1. **Straight D-box**: Takes n inputs, permutes them, and produces n outputs. Each input bit appears exactly once in the output [1][5]. Also called as P Block.
2. **Compression D-box**: Has n inputs and m outputs, where m  n. Some input bits connect to multiple outputs, increasing the number of bits for the next stage[1][5].

### S-Boxes (Substitution Boxes)
S-boxes are the nonlinear components of block ciphers that perform substitution[1][5][8]. They:
- Take n-bit input and produce m-bit output (n and m are not necessarily equal)
- Can be implemented as lookup tables
- May use fixed tables (as in DES) or dynamically generated tables (as in Blowfish)
- Provide the core security of ciphers like DES - without them, the cipher would be linear and easily broken[4][8]

S-boxes are designed to resist cryptanalytic attacks by having properties such as:
- High nonlinearity
- Low differential uniformity
- Good avalanche effect (small input changes cause significant output changes)

## Modes of Operation

Since block ciphers only encrypt fixed-size blocks, various modes of operation are used for longer messages:

1. **Electronic Codebook (ECB)**: Simplest mode where each block is encrypted independently
2. **Cipher Block Chaining (CBC)**: Each block is XORed with the previous ciphertext block before encryption
3. **Cipher Feedback (CFB)**: Emulates a self-synchronizing stream cipher
4. **Output Feedback (OFB)**: Creates a keystream by repeatedly encrypting an initialization vector
5. **Counter (CTR)**: Creates a keystream by encrypting sequential counter values[7]

All modes except ECB provide semantic security under chosen plaintext attacks[7].


# References

Citations:
[1] https://www.tutorialspoint.com/what-are-the-components-of-modern-block-cipher-in-information-security
[2] https://www.tutorialspoint.com/difference-between-substitution-cipher-technique-and-transposition-cipher-technique
[3] https://www.open.edu/openlearn/digital-computing/network-security/content-section-4.3
[4] https://uomustansiriyah.edu.iq/media/lectures/6/6_2024_10_11!08_21_19_PM.pdf
[5] https://www.tutorialspoint.com/cryptography/cryptography_block_cipher.htm
[6] https://cacr.uwaterloo.ca/hac/about/chap7.pdf
[7] https://en.wikipedia.org/wiki/Block_cipher
[8] https://en.wikipedia.org/wiki/S-box
[9] https://www.umsl.edu/~siegelj/information_theory/projects/des.netau.net/Dataencryptionstandard.html
[10] https://study.com/academy/lesson/block-cipher-definition-purpose-examples.html
[11] https://en.wikipedia.org/wiki/Substitution_cipher
[12] https://www.sangfor.com/glossary/cybersecurity/what-is-block-cipher
[13] https://www.scribd.com/document/427924098/6-Introduction-to-Modern-Block-Ciphers
[14] https://www.tutorialspoint.com/cryptography/block_cipher.htm
[15] https://www.youtube.com/watch?v=UB19DOkODSw
[16] https://www.sciencedirect.com/topics/computer-science/block-cipher
[17] https://www.techtarget.com/searchsecurity/definition/block-cipher
[18] https://www.slideshare.net/slideshow/topic1-substitution-transpositiontechniques/249936823
[19] https://www.wolfssl.com/what-is-a-block-cipher-3/
[20] https://crypto.stackexchange.com/questions/33556/what-is-the-difference-between-substitution-cipher-and-block-cipher
[21] http://friedo.szm.sk/krypto/rsa/tr-601.pdf
[22] https://fr.scribd.com/presentation/426090258/Introduction-to-Modern-Symmetric-key-Ciphers
[23] https://pravin-hub-rgb.github.io/BCA/resources/sem5/crypto/unit2/index.html
[24] https://www.baeldung.com/cs/stream-cipher-vs-block-cipher
[25] http://almuhammadi.com/sultan/books_2020/Forouzan.pdf
[26] https://www.slideshare.net/slideshow/ch05ppt-255979900/255979900
[27] https://www.scribd.com/presentation/816747279/Week-5-1-Cryptography-Block-Ciphers
[28] https://dpvipracollege.in/wp-content/uploads/2023/01/Data-Communications-and-Networking-By-Behrouz-A.Forouzan.pdf
[29] https://daxinimehul321.files.wordpress.com/2014/11/cryptography-and-network-security-forouzan-copy.pdf
[30] https://www.slideshare.net/slideshow/ch05ppt-255564127/255564127

---
Answer from Perplexity: pplx.ai/share

###### Information
- date: 2025.05.05
- time: 07:19