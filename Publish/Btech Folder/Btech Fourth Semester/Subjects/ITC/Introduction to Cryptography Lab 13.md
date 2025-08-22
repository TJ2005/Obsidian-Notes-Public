# **Experiment 10: El Gamal Cryptosystem**

### **Aim:**

Develop a program to implement the El Gamal cryptosystem.

### **Learning Outcomes:**

After completing this experiment, students will be able to:

1. Explain how the El Gamal cryptosystem works.
    
2. Understand where El Gamal is used, along with its strengths and limitations.
    

---

# **Theory:**

The El Gamal cryptosystem is a type of asymmetric encryption based on the Discrete Logarithm Problem (DLP). Its security relies on the difficulty of solving these logarithms, making it a reliable option for both encrypting information and creating digital signatures.

---

# **Python Code (with Explanations):**

```python
# El Gamal Cryptosystem Implementation in Python

def mod_inverse(a, p):
    # Finds modular inverse using the Extended Euclidean Algorithm
    for x in range(1, p):
        if (a * x) % p == 1:
            return x
    return None

def key_generation(p, g, x):
    # Generates public and private keys
    y = pow(g, x, p)
    return (p, g, y), x  # Returning public_key and private_key

def encrypt(public_key, M, k):
    p, g, y = public_key
    C1 = pow(g, k, p)
    C2 = (M * pow(y, k, p)) % p
    return (C1, C2)

def decrypt(private_key, p, C1, C2):
    x = private_key
    S = pow(C1, x, p)
    S_inv = mod_inverse(S, p)
    M = (C2 * S_inv) % p
    return M

# Example to demonstrate working
if __name__ == "__main__":
    # Initial values
    p = 23
    g = 5
    x = 6  # Private key
    M = 10  # Message to encrypt
    k = 3   # Random ephemeral key

    # Key Generation
    public_key, private_key = key_generation(p, g, x)
    print(f"Public Key (p, g, y): {public_key}")
    print(f"Private Key (x): {private_key}")

    # Encryption
    C1, C2 = encrypt(public_key, M, k)
    print(f"Ciphertext: (C1, C2) = ({C1}, {C2})")

    # Decryption
    decrypted_message = decrypt(private_key, p, C1, C2)
    print(f"Decrypted Message: {decrypted_message}")
```

---

# **Questions and Answers:**

### 1. Why is the generator g usually a small number even when p is large?

The generator **g** is kept small to make calculations faster and more manageable, especially for repeated operations like exponentiation. Even though it’s small, it still spans the whole group thanks to its mathematical properties, keeping the system secure.

---

### 2. How does the choice of k affect the security of the ciphertext?

The random number **k** needs to be different and unpredictable each time encryption happens.

- If **k** is reused or guessed, it can lead to attacks where someone figures out the private key or the message itself.
    
- A strong, random **k** ensures that encrypting the same message twice will give completely different ciphertexts, boosting security.
    

---

### 3. Is El Gamal efficient for short messages? If not, how is it typically used?

El Gamal is **not ideal for short messages** because the resulting ciphertext can be quite large compared to the original message.  
To solve this:

- El Gamal is mostly used to encrypt a small symmetric key.
    
- That symmetric key (for example, an AES key) is then used to encrypt the actual data.  
    This combination is called **hybrid encryption**.
    

---

### 4. How does El Gamal provide confidentiality but not message integrity? How can both be achieved?

El Gamal ensures **confidentiality** by making sure only the intended recipient can decrypt the data.  
However, it doesn’t automatically protect against tampering — someone could alter the ciphertext without being detected.  
To guarantee both confidentiality and integrity:

- We can pair El Gamal with digital signatures and hash functions.
- Example: Encrypt the data and sign it with **DSA** or **ECDSA** to ensure it wasn’t changed in transit.

---

# **Conclusion:**

Through this experiment, I successfully coded the El Gamal cryptosystem in Python.  
I learned how encryption and decryption rely on modular math and the difficulty of solving discrete logarithms.  
I also realized the importance of using a unique random value (**k**) for each encryption to keep the system secure.  
This lab gave me a hands-on understanding of how asymmetric cryptography works in real-world security applications.
