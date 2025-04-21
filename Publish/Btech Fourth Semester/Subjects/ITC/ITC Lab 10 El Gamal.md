---
Title: "Lab 10 El Gamal"
Status: 
marker: 
tags: 
Date: "2025.04.02"
Time: "10:30"
---
### El Gamal Cryptosystem - Python Implementation

```python
def power_mod(base, exp, mod):
    result = 1
    while exp > 0:
        if exp % 2 == 1:
            result = (result * base) % mod
        base = (base * base) % mod
        exp //= 2
    return result


def mod_inverse(a, p):
    return power_mod(a, p-2, p)  # Fermat's little theorem: a^(p-2) mod p is the inverse of a mod p

# Key Generation
def key_generation(p, g, x):
    y = power_mod(g, x, p)
    return (y)

# Encryption
def encryption(p, g, y, M, k):
    C1 = power_mod(g, k, p)
    C2 = (M * power_mod(y, k, p)) % p
    return (C1, C2)

# Decryption
def decryption(p, C1, C2, x):
    S = power_mod(C1, x, p)
    S_inv = mod_inverse(S, p)
    M = (C2 * S_inv) % p
    return M


p = 23
g = 5
x = 6  # Private key

# Public key generation
y = key_generation(p, g, x)
print(f"Public Key: (p = {p}, g = {g}, y = {y})")
print(f"Private Key: x = {x}")

# Example 2 - Encryption and Decryption
M = 10  # Message
k = 3   # Random number

# Encryption
C1, C2 = encryption(p, g, y, M, k)
print(f"Ciphertext: (C1 = {C1}, C2 = {C2})")

# Decryption
M_decrypted = decryption(p, C1, C2, x)
print(f"Decrypted Message: {M_decrypted}")
```


### Output:

```
Public Key: (p = 23, g = 5, y = 8)
Private Key: x = 6
Ciphertext: (C1 = 10, C2 = 14)
Decrypted Message: 10
```

---

### Answers to Questions:

1. **Why is the generator g typically a small number even though p is large?**
    
    - A small number is easier to manage and has the necessary mathematical properties to generate large numbers modulo `p`. The large prime `p` ensures the security of the cryptosystem, while a small `g` makes it easier to compute.
        
2. **How does the selection of k affect the security of the ciphertext?**
    
    - The selection of `k` is crucial for security. If `k` is chosen poorly, an attacker could gain information about the private key or the original message. Reusing `k` makes the system vulnerable to attacks like the **plaintext attack**.

3. **Can El Gamal encryption be used for short messages? If not, how is it typically handled?**
    
    - El Gamal encryption is not ideal for encrypting short messages directly because the encryption of each message uses a random `k`, and this randomization increases the ciphertext size. 
        
4. **How does El Gamal ensure confidentiality but not message integrity? Which cryptographic techniques can be combined with El Gamal to ensure both?**
    
    - El Gamal provides **confidentiality** because it encrypts the message in such a way that only someone with the private key can decrypt it. 
        

---

### Conclusion:

In this experiment, I learned how the El Gamal cryptosystem works in encrypting and decrypting messages using asymmetric encryption. The process involves key generation, encryption, and decryption, with a focus on the discrete logarithm problem for security. The experiment helped me understand how the choice of parameters like the prime `p`, the generator `g`, and the random integer `k` affect the system's security. Additionally, I grasped how El Gamal provides confidentiality but needs additional techniques (like digital signatures) to ensure both confidentiality and integrity.

era

# References


###### Information
- date: 2025.04.02
- time: 10:30