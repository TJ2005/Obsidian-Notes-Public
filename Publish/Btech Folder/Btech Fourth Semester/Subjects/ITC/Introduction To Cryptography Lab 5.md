---
Title: "Introduction To Cryptography Lab 5"
Status: 
marker: 
tags: 
Date: "2025.02.17"
Time: "14:26"
---
# Introduction To Cryptography Lab 5
# Diffie-Hellman Key Exchange Implementation
```python
def diffie_hellman():
    # Publicly shared prime number and base
    p = 23  # A prime number
    g = 5   # A primitive root modulo p

    # Private keys for Alice and Bob
    private_key_alice = 6  # Alice's private key
    private_key_bob = 15   # Bob's private key

    # Compute public keys
    public_key_alice = (g ** private_key_alice) % p
    public_key_bob = (g ** private_key_bob) % p

    # Exchange public keys (in real scenarios, this would be done over a network)
    # Alice computes the shared secret using Bob's public key
    shared_secret_alice = (public_key_bob ** private_key_alice) % p

    # Bob computes the shared secret using Alice's public key
    shared_secret_bob = (public_key_alice ** private_key_bob) % p

    # Both should have the same shared secret
    assert shared_secret_alice == shared_secret_bob

    print(f"Shared Secret (Alice): {shared_secret_alice}")
    print(f"Shared Secret (Bob): {shared_secret_bob}")

```


![[IMG-20250730000528683.png]]
## QNA
### 1. Discrete Log Problem

The Discrete Logarithm Problem (DLP) is a mathematical problem where, given a prime , a base and a value, we find an integer such that \( $g^x \equiv h \ (\text{mod} \ p$) \). The difficulty of solving this problem underpins the security of many cryptographic protocols, including Diffie-Hellman.

### 2. Elliptic Curve Diffie-Hellman (ECDH)

ECDH modifies the original Diffie-Hellman protocol by using elliptic curves instead. This allows for shorter key lengths with equivalent security, improving efficiency and performance, especially on constrained devices.

### 3. Key Exchange Algorithm Vulnerabilities

Key exchange algorithms are susceptible to **man-in-the-middle (MITM) attacks**. To prevent these, use digital certificates and public key infrastructure (PKI) to authenticate the communicating parties, ensuring that the public keys are genuine.

### 4. Static vs. Ephemeral Diffie-Hellman

- **Static DH:** Uses long-term static keys, which can be recycled across multiple sessions. This is less secure if the private key is compromised.
- **Ephemeral DH (DHE):** Generates temporary, short-lived keys for each session, enhancing security by ensuring that key compromise does not affect past or future sessions.

### Conclusion

The Diffie-Hellman key exchange protocol in its elliptic curve variant (ECDH), is an important tool in secure communications. While susceptible to MITM attacks, proper authentication mechanisms can mitigate these risks. The choice between static and ephemeral DH depends on the balance between security and efficiency needed for the application. 



# References


###### Information
- date: 2025.02.17
- time: 14:26