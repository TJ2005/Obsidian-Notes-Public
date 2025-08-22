---
Title: Goals of cryptography, principles of modern cryptography
Status: true
marker:
  - "[[Introduction To Cryptography (ITC)]]"
  - "[[ITC Unit 1]]"
tags:
  - BTech
  - Note
Date: 2025.04.19
Time: 11:50
---
# Goals of Cryptography

> [!Related Notes]
>  - [[Introduction, Security goals (CIA triad)]]
>  - [[Perfectly secret encryption, one time pad and Shannon’s theorem]]
>  - [[Cryptographic applications]]

Cryptography builds upon the [[Introduction, Security goals (CIA triad)#The CIA Triad|CIA triad]] and extends it with additional security goals:

1. **[[Introduction, Security goals (CIA triad)#Confidentiality|Confidentiality]]**
    - Protecting sensitive data from unauthorized access
    - Preventing eavesdropping
    - Ensuring privacy in communication and transactions
2. **[[Introduction, Security goals (CIA triad)#Integrity|Integrity]]**
    - Guaranteeing data authenticity and reliability
    - Preventing tampering
    - Ensuring that data is consistent and unaltered
3. **Authentication**
    - Verifying the identity of individuals or entities
    - Ensuring that parties are who they claim to be
    - Preventing impersonation and fraud
4. **Non-repudiation**
    - Providing proof of origin and actions
    - Ensuring that a sender cannot deny sending a message or performing an action
    - Enhancing accountability and trust

These goals form the foundation for [[Perfectly secret encryption, one time pad and Shannon’s theorem|cryptographic techniques]] and enable various [[Cryptographic applications|applications]].

# Principles of Modern Cryptography
Modern cryptography is built on several key principles that ensure the security and effectiveness of cryptographic systems:

## Key Management
Generating, storing, and distributing cryptographic keys securely is paramount. This ensures that keys are not compromised and remain confidential. Proper key management is essential for maintaining the security of encrypted data.

## Cryptographic Protocols
Secure communication and transactions rely on protocols that ensure confidentiality, integrity, and authentication at each stage of the process. These protocols define how cryptographic algorithms are used in practice.

## Cipher Design
Ciphers must be robust against known attacks and resistant to future cryptanalysis. Secure algorithms should withstand attempts to break them. This includes considerations for:

- Algorithm strength
- Resistance to various attack vectors
- Computational efficiency


## Security Proofs
Mathematical proofs help demonstrate the strength and security of cryptographic algorithms. This provides confidence in their resilience against attacks. Security proofs are particularly important in establishing the theoretical security of cryptographic systems like the [[Perfectly secret encryption, one time pad and Shannon’s theorem#One-Time Pad|one-time pad]].



# References


###### Information
- date: 2025.04.19
- time: 11:50