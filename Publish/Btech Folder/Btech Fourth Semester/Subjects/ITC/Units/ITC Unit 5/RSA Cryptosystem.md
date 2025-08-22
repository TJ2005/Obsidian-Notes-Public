---
Title: "RSA Cryptosystem"
Status: 
marker: 
tags: 
Date: "2025.05.02"
Time: "09:48"
---
# RSA Cryptosystem
Its April 1977 Ronald Rivest, Adle Shamir, Len Adleman had made use of the concepts introduced by Diffie Hellman to solve the crisis of encrypting messages in the forecoming future which they knew would be dependant of Internet Messaging.

---

- Introduces a public-key encryption method where revealing the encryption key does **not** reveal the decryption key.
- **Implication 1:** No need for secure key exchange-anyone can encrypt a message using the recipient's public key.
- **Implication 2:** Digital signatures are possible-messages can be signed with a private key and verified with the public key.
- Enables authentication and non-repudiation-signatures can't be forged, and the signer can’t deny them.

- **Encryption:** Message is a number $M$, encrypted as $C = M^e \bmod n$, where $n = p \times q$ (large secret primes).
- **Decryption:** Uses private exponent $d$, with $e \times d \equiv 1 \pmod{(p-1)(q-1)}$.

- **Security:** Depends on the difficulty of factoring the public modulus $n$.
- **Applications:** Electronic mail, message-passing, electronic funds transfer.

---


# RSA Encryption Process with Alice and Bob

The RSA cryptosystem, developed by Rivest, Shamir, and Adleman, works through the following process:

## Key Generation (Alice's Steps)
1. Alice selects two large prime numbers $p$ and $q$ (privately)
2. She computes $n = p \times q$ (the modulus)
3. She calculates $\phi(n) = (p-1)(q-1)$ (Euler's totient function)
4. She chooses a public exponent $e$ such that $1 < e < \phi(n)$ and $\gcd(e, \phi(n)) = 1$
5. She computes private exponent $d$ such that $e \times d \equiv 1 \pmod{\phi(n)}$
6. Alice publishes her public key $(e, n)$ in a public directory while keeping her private key $(d, n)$ secret [1]

## Communication Process

**For Bob to send a message to Alice:**
1. Bob obtains Alice's public key $(e, n)$ from the public directory
2. He converts his message $M$ into a number $m$ (where $0 \leq m < n$)
3. He encrypts the message by computing ciphertext $c \equiv m^e \pmod{n}$
4. Bob sends ciphertext $c$ to Alice [1][2]

**For Alice to decrypt Bob's message:**
1. Alice uses her private key $d$ to compute $m \equiv c^d \pmod{n}$
2. She converts $m$ back to the original message $M$ [1][2]

## Security Against Attackers

An attacker who intercepts the ciphertext $c$ cannot decrypt it without knowing the private key $d$. Even though the attacker knows the public key $(e, n)$, determining $d$ requires:
- Factoring $n$ into its prime components $p$ and $q$
- Computing $\phi(n) = (p-1)(q-1)$
- Finding $d$ such that $e \times d \equiv 1 \pmod{\phi(n)}$

The security of RSA relies on the computational difficulty of factoring large numbers. With sufficiently large primes (typically 100+ digits each), factoring $n$ becomes computationally infeasible with current technology [1].

## Example
If Bob wants to send "HELLO" to Alice:
1. Bob converts "HELLO" to a number (e.g., $m = 676584$)
2. Using Alice's public key $(e, n)$, Bob computes $c = m^e \bmod n$
3. Bob sends $c$ to Alice
4. Alice computes $m = c^d \bmod n$ using her private key
5. Alice converts $m$ back to "HELLO"  [5] [6]


# References

Citations:
[1] https://dspace.mit.edu/bitstream/handle/1721.1/148910/MIT-LCS-TM-082.pdf?sequence=1&isAllowed=y
[2] https://en.wikipedia.org/wiki/RSA_cryptosystem
[3] https://www.studocu.com/en-gb/messages/question/2454091/alice-and-bob-are-going-to-communicate-using-the-rsa-system-alice-has-chosen-primes-p-and-q-and
[4] https://www.techtarget.com/searchsecurity/definition/RSA
[5] https://eitca.org/cybersecurity/eitc-is-ccf-classical-cryptography-fundamentals/introduction-to-public-key-cryptography/the-rsa-cryptosystem-and-efficient-exponentiation/in-rsa-cipher-does-alice-need-bob-public-key-to-encrypt-a-message-to-bob/
[6] https://brilliant.org/wiki/rsa-encryption/
[7] https://www.techtarget.com/searchsecurity/definition/RSA
[8] https://www.cs.purdue.edu/homes/clg/CS590/files/public-key-notes.pdf
[9] https://dspace.mit.edu/bitstream/handle/1721.1/30576/MIT-CSAIL-TR-2005-066.pdf?sequence=2
[10] https://brilliant.org/wiki/rsa-encryption/
[14] https://www.encryptionconsulting.com/diffie-hellman-key-exchange-vs-rsa/
[16] https://en.wikipedia.org/wiki/Public-key_cryptography
[17] https://www.preveil.com/blog/public-and-private-key/
[19] https://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange
[20] https://wordtothewise.com/2014/09/cryptography-alice-bob/
[21] https://textbook.cs161.org/crypto/public-key.html
[22] https://www.practicalnetworking.net/series/cryptography/using-asymmetric-keys/
[25] https://dspace.mit.edu/bitstream/handle/1721.1/91676/6-857-fall-2003/contents/exams/2003_midtermsols.pdf
[26] https://dspace.mit.edu/bitstream/handle/1721.1/52767/503456131-MIT.pdf;jsessionid=09574838AE2991A0021C1824C94BB48D?sequence%3D2
[27] https://dspace.mit.edu/bitstream/handle/1721.1/36344/MIT-CSAIL-TR-2007-013.pdf?sequence=1
[28] https://dspace.mit.edu/bitstream/handle/1721.1/121443/10.1.1.443.6190.pdf?sequence=2&isAllowed=y
[29] https://eitca.org/cybersecurity/eitc-is-ccf-classical-cryptography-fundamentals/introduction-to-public-key-cryptography/the-rsa-cryptosystem-and-efficient-exponentiation/in-rsa-cipher-does-alice-need-bob-public-key-to-encrypt-a-message-to-bob/
[30] https://www.usna.edu/Users/cs/wcbrown/courses/si110AY13S/lec/l26/lec.html
[31] https://dspace.mit.edu/bitstream/handle/1721.1/130798/1252202600-MIT.pdf?sequence=1&isAllowed=y
[32] https://crypto.stackexchange.com/questions/99818/can-bob-and-alice-do-an-authenticated-diffie-hellman-key-exchange-if-bob-only-kn

---


###### Information
- date: 2025.05.02
- time: 09:48