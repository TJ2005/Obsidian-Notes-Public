---
Title: "Introduction to Cryptography Lab 6"
Status: 
marker: 
tags: 
Date: "2025.03.10"
Time: "12:42"
---

### **Experiment 6: RSA Algorithm**
RSA

### **Code**

#### **Encryption:**

```python
from sympy import isprime
import math

e = 0
p = int(input("Enter p: "))
q = int(input("Enter q: "))
n = p * q

if isprime(p) and isprime(q):
    et = (p - 1) * (q - 1)
    
    for i in range(2, et):
        if math.gcd(i, et) == 1 and math.gcd(i, q - 1) == 1 and math.gcd(i, p - 1) == 1:
            e = i
            break

    if e == 0:
        print("No valid e found for this!")
    else:
        print(f"Chosen e: {e}")
        d = 0

        for k in range(1, et):
            if (e * k) % et == 1 and e != k:
                d = k
                break

        if d == 0:
            print("No valid d found for this!")
        else:
            print(f"Calculated d: {d}")
            print(f"Public Key: (n={n}, e={e})")
            print(f"Private Key: (n={n}, d={d})")

            pt = int(input("Enter plaintext: "))
            
            # Encrypting
            print("Encrypted message =", pow(pt, e, n))
else:
    print("p or q are not prime")
```

---

#### **Decryption:**

```python
from sympy import isprime
import math

e = 0
p = int(input("Enter p: "))
q = int(input("Enter q: "))
n = p * q

if isprime(p) and isprime(q):
    et = (p - 1) * (q - 1)

    for i in range(2, et):
        if math.gcd(i, et) == 1 and math.gcd(i, q - 1) == 1 and math.gcd(i, p - 1) == 1:
            e = i
            break

    if e == 0:
        print("No valid e found for this!")
    else:
        print(f"Chosen e: {e}")
        d = 0

        for k in range(1, et):
            if (e * k) % et == 1 and e != k:
                d = k
                break

        if d == 0:
            print("No valid d found for this!")
        else:
            print(f"Calculated d: {d}")
            print(f"Public Key: (n={n}, e={e})")
            print(f"Private Key: (n={n}, d={d})")

            ct = int(input("Enter cipher text: "))
            
            # Decrypting
            print("Decrypted message =", pow(ct, d, n))
else:
    print("p or q are not prime")
```

---

### **Questions**

**1. Why is it computationally difficult to derive the private key from the public key in RSA?**  
RSA's security is based on the challenge of **factoring large composite numbers**. The public key contains the modulus nn, which is the product of two large primes pp and qq. While multiplying two primes is easy, factoring nn back into pp and qq is computationally infeasible.

---

**2. What happens if two different users select the same prime numbers for their RSA key pairs?**  
If two users choose the same prime numbers, their **public modulus nn** will be identical. This makes the system vulnerable, as one user's private key could be used to **decrypt** the other’s messages.

---

**3. How does RSA handle message sizes larger than the modulus nn?**  
RSA cannot encrypt messages larger than the modulus nn. For larger messages:

- The message is **split into smaller blocks**.
    
- Each block is individually encrypted using RSA.
    
- Modes like **hybrid encryption** (RSA + symmetric encryption) are used for large data.
    

---

**4. How does the Chinese Remainder Theorem (CRT) optimize RSA decryption?**  
The **Chinese Remainder Theorem (CRT)** speeds up decryption by:

- **Splitting the decryption** into two smaller exponentiations using pp and qq.
- Combining the results, making decryption **4x faster**.
    

---

**5. Why does RSA encryption work as a one-way function, and how does the difficulty of integer factorization contribute to its security?**  
RSA works as a **one-way function** due to the difficulty of factoring large numbers.

- **Forward operation (encryption)**: Multiplying large primes is easy.
    
- **Reverse operation (decryption)**: Factoring large composite numbers is extremely hard, ensuring security.