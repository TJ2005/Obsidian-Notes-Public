---
Title: Introduction to Cryptography Lab 3
Status: 
marker: 
tags: 
Date: 2025.01.20
Time: 12:32
---


---

### Experiment 3: Affine Cipher

**Aim**: To study and implement the Affine Cipher.

**Learning Outcomes**:

1. Understand steps of the Affine Cipher.
2. Implement the Affine Cipher.
3. Understand variations of the Affine Cipher and its effectiveness.

---

### **Theory**:

The Affine Cipher is a type of monoalphabetic substitution cipher. Each letter in an alphabet is mapped to its numeric equivalent, encrypted using a mathematical function, and then converted back to a letter.

The formula used is:

- **Encryption**:
    
$$    E(x)=(ax+b)mod  mE(x) = (ax + b) \mod m$$
- **Decryption**:
    
$$    D(x)=a−1(x−b)mod  mD(x) = a^{-1} (x - b) \mod m$$

Where:

- **m** = size of the alphabet (typically 26 for the English alphabet)
- **a** and **b** are the keys.
- **a^{-1}** is the modular inverse of **a** modulo **m**.

---

### **Encryption Example**:

Given **a = 17** and **b = 20**:

- **Plaintext**: "TWENTYFIFTEEN" → Corresponding numbers: 19, 22, 4, 13, 19, 24, 5, 8, 5, 4, 19, 5, 4, 4, 13
- **Encrypted Text**: Using the formula (ax+b)mod  26(ax + b) \mod 26, the encrypted text will be: "FFKHFMBABFKKH".

---

### **Code Explanation**:

The code provides functions to:

- **Encrypt**: Convert plaintext to its numeric equivalent, apply the affine formula, and convert it back to letters.
- **Decrypt**: Reverse the encryption by using the modular inverse of **a**.

```python
from sympy import isprime

# Function to find modular inverse of 'a' modulo 26
def mod_inverse(a, m):
    for i in range(1, m):
        if (a * i) % m == 1:
            return i
    return 0  # Return None if no inverse exists

# Encrypt function
def encrypt(plaintext, a, b):
    encrypted_text = ""
    for char in plaintext:
        if char.isalpha():
            is_upper = char.isupper()
            x = ord(char.upper()) - ord('A')
            encrypted_char = (a * x + b) % 26
            encrypted_text += chr(encrypted_char + (ord('A') if is_upper else ord('a')))
        else:
            encrypted_text += char
    return encrypted_text

# Decrypt function
def decrypt(ciphertext, a, b):
    decrypted_text = ""
    a_inv = mod_inverse(a, 26)
    if a_inv == 0:
        return "Inverse does not exist, decryption impossible."
    for char in ciphertext:
        if char.isalpha():
            is_upper = char.isupper()
            y = ord(char.upper()) - ord('A')
            decrypted_char = (a_inv * (y - b)) % 26
            decrypted_text += chr(decrypted_char + (ord('A') if is_upper else ord('a')))
        else:
            decrypted_text += char
    return decrypted_text

# Sample input
plaintext = input("Enter the plaintext: ")
while True:
    a = int(input("Enter a value for 'a' (make sure it's prime): "))
    if isprime(a):
        break
    else:
        print("Invalid input. 'a' must be a prime number.")
b = int(input("Enter a value for 'b': "))
encrypted = encrypt(plaintext, a, b)
print("Encrypted Text: " + encrypted)
decrypted = decrypt(encrypted, a, b)
print("Decrypted Text: " + decrypted)
```

---

### **Output**:

- **Input**:
    
    ```
    Enter the plaintext: TWENTYFIFTEEN
    Enter a value for 'a' (make sure it's prime): 17
    Enter a value for 'b': 20
    ```
    
- **Encrypted Text**:
    
    ```
    Encrypted Text: FFKHFMBABFKKH
    ```
    
- **Decrypted Text**:
    
    ```
    Decrypted Text: TWENTYFIFTEEN
    ```
    

---

### **Questions**:

1. **If the plaintext "HELLO" encrypts to "AXEEH", determine the keys a and b?**
    
    - To solve this, you would need to set up a system of linear equations based on the encryption formula and solve for **a** and **b** using the known ciphertext and plaintext.
2. **What are the common types of attacks on the Affine Cipher?**
    
    - **Frequency Analysis**: Since it’s a substitution cipher, frequency analysis can help deduce the keys.
    - **Brute Force**: Trying all possible values for **a** and **b** since **a** must be coprime with 26.
3. **What is a Three Pass Protocol? How does it help in the Affine Cipher?**
    
    - A **Three Pass Protocol** involves the encryption and decryption of a message in three stages, ensuring that even if an attacker intercepts the message, they cannot easily decrypt it. It adds an extra layer of security.
4. **Compare Vigenere Cipher and Affine Cipher w.r.t the following paper**:
    
    - Vigenère Cipher is polyalphabetic (uses multiple cipher alphabets), whereas Affine Cipher is monoalphabetic (uses a single alphabet).
    - Vigenère Cipher is considered more secure than Affine Cipher because of the use of a key phrase that changes the cipher alphabet for each letter in the plaintext.

---
