---
Title: "Attack List"
Status: 
marker: 
tags: 
Date: "2025.05.05"
Time: "07:43"
---

# Attacks on Information Security

## Types of Attacks Based on Security Goals
Security attacks can be categorized based on which aspect of the CIA triad they threaten:

### Threats to Confidentiality
- **Snooping**: Unauthorized access or interception of data, which can be countered using encryption.
- **Traffic Analysis**: Monitoring communication patterns to extract information even when data is encrypted.

### Threats to Integrity
- **Modification**: Intercepting and altering information for the attacker's benefit.
- **Masquerading/Spoofing**: Impersonating another entity to gain unauthorized access.
- **Replaying**: Capturing valid messages and retransmitting them later for malicious purposes.
- **Repudiation**: Denial by a sender or receiver that they sent or received a message.

### Threats to Availability
- **Denial of Service (DoS)**: Disrupting system services by overwhelming resources, intercepting responses, or causing clients to overload the system.

## Passive vs. Active Attacks

### Passive Attacks
- Target confidentiality through snooping and traffic analysis
- Do not modify data or harm system functionality
- Difficult to detect but can be prevented through encryption
- System continues normal operation

### Active Attacks
- Target integrity and availability
- Change data or harm system functionality
- Easier to detect than prevent
- Include modification, masquerading, replaying, repudiation, and denial of service

Understanding these attack categories helps in developing appropriate security measures for different types of threats.


---
Answer from Perplexity: pplx.ai/share

# Differential and Linear Cryptanalysis of Block Ciphers

## Differential Cryptanalysis

Differential cryptanalysis is a chosen-plaintext attack developed by Eli Biham and Adi Shamir that analyzes how differences in plaintext pairs affect differences in resulting ciphertext pairs.

### Key Concepts:
- Examines the relationship between plaintext differences ($P_1 \oplus P_2$) and ciphertext differences ($C_1 \oplus C_2$)
- Creates a differential distribution table (XOR profile) showing probabilities of specific output differences given input differences
- Exploits non-uniform distribution in these tables caused by weaknesses in S-box structures

### Example with Simple XOR:
For a simple XOR operation with key $K$:
$C_1 = P_1 \oplus K$
$C_2 = P_2 \oplus K$
$C_1 \oplus C_2 = P_1 \oplus P_2$

### Attack Procedure:
1. Create differential distribution tables for each S-box
2. Combine probabilities to build distribution for entire cipher
3. Choose plaintexts with highest probability differences
4. Analyze results to determine key bits
5. Repeat until sufficient key bits are found
6. Use brute force for remaining bits

## Linear Cryptanalysis

Linear cryptanalysis, introduced by Mitsuru Matsui in 1993, uses known-plaintext attacks to find linear approximations of cipher components.

### Key Concepts:
- Seeks linear relationships between plaintext, ciphertext, and key bits
- Creates equations of the form:
  $(k_0 \oplus k_1 \oplus \ldots \oplus k_x) = (p_0 \oplus p_1 \oplus \ldots \oplus p_y) \oplus (c_0 \oplus c_1 \oplus \ldots \oplus c_z)$
- Each equation should hold with probability $\frac{1}{2} + \varepsilon$, where $\varepsilon$ is the bias
- Larger bias values indicate more effective equations

### Example with Linear S-box:
For a simple cipher with linear S-box:
$c_0 = p_0 \oplus k_0 \oplus p_1 \oplus k_1$
$c_1 = p_0 \oplus k_0 \oplus p_1 \oplus k_1 \oplus p_2 \oplus k_2$
$c_2 = p_1 \oplus k_1 \oplus p_2 \oplus k_2$

Solving for key bits:
$k_1 = p_1 \oplus (c_0 \oplus c_1 \oplus c_2)$
$k_2 = p_2 \oplus (c_0 \oplus c_1)$
$k_0 = p_0 \oplus (c_1 \oplus c_2)$

Both attacks exploit structural weaknesses in block ciphers, particularly in S-box design, demonstrating why modern ciphers need carefully designed components to resist cryptanalysis.

Citations:
[1] https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/64371909/7496fda0-48e0-4863-b5db-72942ac3d389/paste.txt

---
Answer from Perplexity: pplx.ai/share

# Security of DES: Analysis of Attack Methods

The Data Encryption Standard (DES) has been subjected to extensive cryptanalysis since its introduction. Three primary attack methods have been identified:

## Brute-Force Attack

DES is vulnerable to brute-force attacks due to its short 56-bit key length. With modern computational resources, this is now entirely feasible:

- The Electronic Frontier Foundation built a DES Cracker in 1998 for less than $250,000 that could find a DES key in approximately 4.5 days on average (worst case: 9 days)[2]
- The theoretical key space of $2^{56}$ (approximately 72 quadrillion keys) is no longer sufficient protection[6]
- The key complement weakness further reduces the effective search space to $2^{55}$ operations[1]

To address this vulnerability, Triple DES (3DES) was developed, using either two keys (112-bit effective key length) or three keys (168-bit effective key length), making brute-force attacks impractical[5].

## Differential Cryptanalysis

Differential cryptanalysis examines how differences in plaintext pairs affect differences in resulting ciphertext pairs:

- DES was specifically designed to resist differential cryptanalysis, which was known to IBM and NSA but kept secret until rediscovered by Biham and Shamir[3][7]
- Breaking full 16-round DES requires $2^{47}$ chosen plaintexts, which is theoretically more efficient than brute force but impractical to implement[3][7]
- Reduced-round versions of DES are more vulnerable (e.g., 8-round DES can be attacked with significantly fewer chosen plaintexts)[3]
- Increasing DES to 20 rounds would require more than $2^{64}$ chosen plaintexts, which exceeds the total possible plaintext space[1]

## Linear Cryptanalysis

Linear cryptanalysis seeks linear approximations between plaintext, ciphertext, and key bits:

- Discovered by Mitsuru Matsui in 1993, this technique was not known to DES designers[4][7]
- DES is more vulnerable to linear cryptanalysis than differential cryptanalysis[1]
- Breaking DES requires $2^{43}$ known plaintexts, which is theoretically feasible but practically challenging[4][7]
- The attack works by finding equations of the form $(k_0 \oplus k_1 \oplus \ldots \oplus k_x) = (p_0 \oplus p_1 \oplus \ldots \oplus p_y) \oplus (c_0 \oplus c_1 \oplus \ldots \oplus c_z)$ that hold with probability $\frac{1}{2} + \varepsilon$, where $\varepsilon$ is the bias[1]

While these theoretical attacks exist, DES is now considered obsolete primarily due to its vulnerability to brute-force attacks rather than cryptanalytic techniques. Modern applications have largely migrated to 3DES or more advanced algorithms like AES.



# Attacks on RSA: A Comprehensive Analysis

RSA's security is based on the computational difficulty of factoring large integers. Despite no devastating attacks being discovered, several potential vulnerabilities exist based on weak parameters, implementation flaws, or mathematical properties.

## Factorization Attacks

The fundamental attack on RSA involves factoring the modulus $n = p \times q$. If an attacker can factor $n$ and obtain $p$ and $q$, they can calculate $\phi(n) = (p-1)(q-1)$ and derive the private key $d = e^{-1} \mod \phi(n)$.

- **Security requirement**: Modulus $n$ should be at least 1024 bits (309 decimal digits)
- **Recommendation**: Each prime ($p$ and $q$) should be at least 512 bits

## Chosen-Ciphertext Attack

This attack exploits RSA's multiplicative property:

1. Attacker intercepts ciphertext $C = P^e \mod n$
2. Chooses random integer $X$ in $Z_n^*$
3. Calculates $Y = C \times X^e \mod n$
4. Gets $Y$ decrypted by the victim to obtain $Z = Y^d \mod n$
5. Calculates $P = Z \times X^{-1} \mod n$

## Encryption Exponent Attacks

Using small encryption exponents (like $e = 3$) can lead to:

- **Coppersmith Theorem Attack**: Can find plaintext roots if one is smaller than $n^{1/e}$
- **Broadcast Attack**: If same message is sent to multiple recipients with same low $e$
- **Related Message Attack**: When two plaintexts are linearly related
- **Short Pad Attack**: When same message is sent with different short random pads

**Recommendation**: Use $e = 65537 = 2^{16}+1$ instead of small values

## Decryption Exponent Attacks

- **Revealed Decryption Exponent**: If $d$ is compromised, attacker can factor $n$
- **Low Decryption Exponent**: If $d < \frac{1}{3}n^{1/4}$ and $q < p < 2q$, $n$ can be factored

**Recommendation**: Always use $d \geq \frac{1}{3}n^{1/4}$

## Plaintext Attacks

- **Short Message Attack**: Attacker tries all possible short messages
- **Cycling Attack**: Repeatedly encrypting ciphertext eventually yields plaintext
- **Unconcealed Message Attack**: Some messages encrypt to themselves

**Recommendation**: Use proper padding (OAEP) for messages

## Modulus Attacks

- **Common Modulus Attack**: When multiple users share the same modulus

**Recommendation**: Each entity should use a unique modulus

## Implementation Attacks

- **Timing Attack**: Analyzes time variations during decryption to reveal private key
- **Power Attack**: Measures power consumption during decryption operations

**Countermeasures**:
1. Add random delays to operations
2. Use blinding: multiply ciphertext by random number before decryption

# References

Would you like me to elaborate on any specific attack or countermeasure?

Citations:
[1] https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/64371909/a270d81a-dcc4-4a42-9f22-81e6bc86e5e1/paste.txt
[2] https://en.wikipedia.org/wiki/RSA_cryptosystem
[3] https://www.iiis.org/cds2009/cd2009sci/RMCI2009/PapersPdf/R873IE.pdf
[4] https://docs.yubico.com/yesdk/users-manual/support/rsa-unpad.html
[5] https://reitermk.github.io/papers/1996/Eurocrypt.pdf
[6] https://crypto.stanford.edu/~dabo/papers/RSA-survey.pdf
[7] https://www.techtarget.com/searchsecurity/definition/RSA
[8] https://www.utc.edu/sites/default/files/2021-04/course-paper-5600-rsa.pdf
[9] https://en.wikipedia.org/wiki/Coppersmith's_attack
[10] https://github.com/ashutosh1206/Crypton/blob/master/RSA-encryption/Attack-Hastad-Broadcast/README.md
[11] https://eprint.iacr.org/2009/205.pdf
[12] https://www.utc.edu/sites/default/files/2021-04/assignment6.pdf
[13] https://cybertalents.com/blog/rsa-encryption
[14] https://websites.nku.edu/~christensen/Mathematical%20attack%20on%20RSA.pdf
[15] https://crypto.stackexchange.com/questions/2323/how-does-a-chosen-plaintext-attack-on-rsa-work
[16] https://cims.nyu.edu/~regev/teaching/lattices_fall_2004/ln/rsa.pdf
[17] http://shainer.github.io/crypto/math/2017/12/03/the-return-of-coppersmith.html
[18] https://crypto.stackexchange.com/questions/52504/deciphering-the-rsa-encrypted-message-from-three-different-public-keys
[19] https://github.com/ashutosh1206/Crypton/blob/master/RSA-encryption/Attack-Franklin-Reiter/README.md
[20] https://crypto.stackexchange.com/questions/80087/short-padding-known-prefix-rsa-attack
[21] https://www.splunk.com/en_us/blog/learn/rsa-algorithm-cryptography.html

---
Answer from Perplexity: pplx.ai/share


Citations:
[1] https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/64371909/7496fda0-48e0-4863-b5db-72942ac3d389/paste.txt
[2] https://www.ietf.org/rfc/rfc4772.txt
[3] https://eitca.org/cybersecurity/eitc-is-ccf-classical-cryptography-fundamentals/des-block-cipher-cryptosystem/data-encryption-standard-des-key-schedule-and-decryption/can-des-be-broken-by-differential-cryptanalysis/
[4] https://en.wikipedia.org/wiki/Linear_cryptanalysis
[5] https://eitca.org/cybersecurity/eitc-is-ccf-classical-cryptography-fundamentals/conclusions-for-private-key-cryptography/multiple-encryption-and-brute-force-attacks/examination-review-multiple-encryption-and-brute-force-attacks/how-does-triple-des-3des-improve-upon-the-security-of-single-and-double-encryption-and-what-are-its-practical-applications/
[6] https://eitca.org/cybersecurity/eitc-is-ccf-classical-cryptography-fundamentals/conclusions-for-private-key-cryptography/multiple-encryption-and-brute-force-attacks/examination-review-multiple-encryption-and-brute-force-attacks/why-is-the-data-encryption-standard-des-considered-vulnerable-to-brute-force-attacks-and-how-does-modern-computational-power-affect-its-security/
[7] https://en.wikipedia.org/wiki/Data_Encryption_Standard
[8] https://serialsjournals.com/abstract/55185_ch-14.pdf
[9] https://crypto.stackexchange.com/questions/37444/what-is-the-point-of-differential-cryptanalysis-when-the-amount-of-necessary-pla
[10] https://eprint.iacr.org/2017/895
[11] https://crypto.stackexchange.com/questions/51629/is-triple-des-still-considered-safe-to-use
[12] https://en.wikipedia.org/wiki/Brute-force_attack
[13] https://www.cs.purdue.edu/homes/ninghui/courses/Fall05/lectures/355_Fall05_lect17.pdf
[14] http://www.cs.bilkent.edu.tr/~selcuk/teaching/cs519/Matsui-LC.pdf
[15] https://www.techtarget.com/searchsecurity/tip/Expert-advice-Encryption-101-Triple-DES-explained
[16] https://crypto.stackexchange.com/questions/5492/brute-force-attack-on-des-property-of-des
[17] https://eprint.iacr.org/2005/084.pdf
[18] https://sites.cs.ucsb.edu/~chris/teaching/cs177/projects/proj6.html
[19] https://en.wikipedia.org/wiki/Triple_DES
[20] https://www.rsaconference.com/library/blog/brute-force-cracking-the-data-encryption-standard
[21] https://home.uncg.edu/cmp/faculty/srtate/580.s17/aeshandout.php

---
Answer from Perplexity: pplx.ai/share


###### Information
- date: 2025.05.05
- time: 07:43