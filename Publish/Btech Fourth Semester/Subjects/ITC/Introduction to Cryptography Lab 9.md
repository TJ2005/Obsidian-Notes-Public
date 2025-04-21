---
Title: "Introduction to Cryptography Lab 9"
Status: 
marker: 
tags: 
Date: "2025.03.10"
Time: "12:49"
---
# Introduction to Cryptography Lab 9

# Questions and answers

```python
import random
from math import gcd

# Generate large prime numbers congruent to 3 mod 4
def generate_prime(bits=8):
    while True:
        p = random.getrandbits(bits)
        if p % 4 == 3 and is_prime(p):
            return p

# Check if a number is prime
def is_prime(n, k=5):  # k is the number of iterations for accuracy
    if n <= 1:
        return False
    if n <= 3:
        return True
    if n % 2 == 0 or n % 3 == 0:
        return False
    i = 5
    while i * i <= n:
        if n % i == 0 or n % (i + 2) == 0:
            return False
        i += 6
    return True

# Extended Euclidean Algorithm
def extended_gcd(a, b):
    if a == 0:
        return b, 0, 1
    gcd, x1, y1 = extended_gcd(b % a, a)
    x = y1 - (b // a) * x1
    y = x1
    return gcd, x, y

# Key generation
def generate_keys():
    p = generate_prime(8)
    q = generate_prime(8)
    while p == q:
        q = generate_prime(8)
    
    n = p * q
    print(f"Public Key: n = {n}")
    print(f"Private Keys: p = {p}, q = {q}")
    return n, p, q

# Encrypt the message
def encrypt(message, n):
    m = int.from_bytes(message.encode(), 'big')
    c = (m ** 2) % n
    return c

# Decrypt the message
def decrypt(ciphertext, p, q, n):
    # Extended Euclidean Algorithm
    gcd, a, b = extended_gcd(p, q)

    # Compute r and s
    r = pow(ciphertext, (p + 1) // 4, p)
    s = pow(ciphertext, (q + 1) // 4, q)

    # Calculate the four potential plaintexts
    x = (a * p * s + b * q * r) % n
    y = (a * p * s - b * q * r) % n

    m1 = x
    m2 = n - x
    m3 = y
    m4 = n - y

    possible_plaintexts = [m1, m2, m3, m4]

    # Convert back to readable text
    decoded_msgs = []
    for m in possible_plaintexts:
        try:
            msg = m.to_bytes((m.bit_length() + 7) // 8, 'big').decode()
            decoded_msgs.append(msg)
        except:
            pass

    return decoded_msgs

# --- Main Execution ---
print("🔑 Generating Keys...")
n, p, q = generate_keys()

# Encrypting a message
plaintext = "Hi"
print(f"\nEncrypting message: {plaintext}")
ciphertext = encrypt(plaintext, n)
print(f"Ciphertext: {ciphertext}")

# Decrypting the message
print("\nDecrypting message...")
decrypted_msgs = decrypt(ciphertext, p, q, n)
print(f"Possible Plaintexts: {decrypted_msgs}")

```

1. **What is the one-way trapdoor function used in the Rabin cryptosystem?**
	- The one way trapdoor function that is used in the Rabin Crypto System is the modular square funct
   - The one-way trapdoor function used in the Rabin cryptosystem is the modular squaring function $C=m^2\mod{n}$.

2. **How does the Rabin cryptosystem differ from RSA in terms of security and computational efficiency?**
   - The Rabin cryptosystem is based on the difficulty of integer factorization, similar to RSA. However, Rabin is more computationally efficient for encryption but more complex for decryption due to the need to resolve ambiguity among four possible plaintexts.

3. **Why is the Rabin cryptosystem classified as a probabilistic asymmetric encryption algorithm?**
   - The Rabin cryptosystem is classified as probabilistic because the decryption process yields four possible plaintexts, requiring additional steps to determine the correct one.

4. **What are some potential attacks against the Rabin cryptosystem, and how can they be mitigated?**
   - Potential attacks include chosen-ciphertext attacks. Mitigation strategies include using padding schemes and ensuring that the plaintext is properly formatted to avoid predictable patterns.
# References


###### Information
- date: 2025.03.10
- time: 12:49