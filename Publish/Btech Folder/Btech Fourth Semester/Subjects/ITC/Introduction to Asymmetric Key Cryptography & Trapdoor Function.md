---
Title: Introduction to Asymmetric Key Cryptography & Trapdoor Function
Status: 
marker:
  - "[[ITC Unit 5]]"
  - "[[ITC Unit 4]]"
tags:
  - BTech
  - Note
Date: 2025.05.05
Time: 07:14
---
# Introduction to Asymmetric Key Cryptography & Trapdoor Function

Asymmetric encryption, also known as public key cryptography, is a cryptographic system that uses a pair of related keys-one public and one private-to encrypt and decrypt data. It's called "asymmetric" because it uses different keys for the encryption and decryption processes, unlike symmetric encryption which uses the same key for both operations[1][4][5].

In asymmetric encryption:
- The public key can be freely shared and is used to encrypt messages
- The private key must be kept secret and is used to decrypt messages
- Data encrypted with the public key can only be decrypted with the corresponding private key[1][5]

This asymmetry eliminates the need for secure key exchange, which is a major security vulnerability in symmetric encryption systems[5].

## Trapdoor Functions

Trapdoor functions are the mathematical foundation of asymmetric cryptography. A trapdoor function is a function that is:
- Easy to compute in one direction
- Extremely difficult to compute in the reverse direction (find its inverse)
- Has a "trapdoor" (special information) that makes it easy to compute the inverse when known[2][3]

For example, if $f$ is a trapdoor function, then given $f(x)$ it's computationally infeasible to find $x$ without knowing the trapdoor information $t$. However, if you know both $f(x)$ and $t$, finding $x$ becomes easy[2].

In asymmetric cryptography, the trapdoor function formula used for encryption becomes the public key, while the secret information (trapdoor) used to compute its inverse becomes the private key[3]. Common examples include:

- [[Publish/Btech Folder/Btech Fourth Semester/Subjects/ITC/RSA Cryptosystem]], which uses modular exponentiation: $$m^e \mod N = c$$ (where finding the original message requires knowing the prime factorization of N)
- Elliptic Curve Cryptography (ECC)
- Digital Signature Algorithm (DSA)[3][5]


# References

Citations:
[1] https://www.techtarget.com/searchsecurity/definition/asymmetric-cryptography
[2] https://en.wikipedia.org/wiki/Trapdoor_function
[3] https://journals.bg.agh.edu.pl/AUTOMAT/2016.20.2/automat.2016.20.2.39.pdf
[4] https://www.cloudflare.com/learning/ssl/what-is-asymmetric-encryption/
[5] https://www.ibm.com/think/topics/asymmetric-encryption
[6] https://www.1kosmos.com/digital-identity-101/encryption/asymmetric-encryption/
[7] https://cpl.thalesgroup.com/faq/key-secrets-management/what-asymmetric-key-or-asymmetric-key-cryptography
[8] https://www.electronicdesign.com/technologies/test-measurement/article/21204923/the-importance-of-trapdoor-functions
[9] https://www.okta.com/identity-101/asymmetric-encryption/
[10] https://deviceauthority.com/symmetric-encryption-vs-asymmetric-encryption/
[11] https://en.wikipedia.org/wiki/Public-key_cryptography
[12] https://www.simplilearn.com/tutorials/cryptography-tutorial/asymmetric-encryption
[13] https://crypto.stackexchange.com/questions/10087/what-is-the-meaning-of-trapdoor-in-cryptography
[14] https://www.youtube.com/watch?v=mxLfrZrXC-g
[15] https://www.baeldung.com/cs/cryptography-trapdoor
[16] https://eprint.iacr.org/2018/529.pdf
[17] https://www.telsy.com/en/the-one-way-and-trapdoor-functions-the-heart-of-modern-encryption/
[18] https://www.youtube.com/watch?v=-hVct0UU-jU

---
Answer from Perplexity: pplx.ai/share



###### Information
- date: 2025.05.05
- time: 07:14