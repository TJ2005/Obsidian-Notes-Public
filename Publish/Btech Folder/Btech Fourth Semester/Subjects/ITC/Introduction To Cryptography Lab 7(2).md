---
Title: "Introduction To Cryptography Lab 4"
Status: 
marker: 
tags: 
Date: "2025.02.17"
Time: "12:47"
---
# Lab 4
Late Submission
Code: type or copy your completed working code here (only 2 x 2 matrix to be taken)
Note: Code should have proper comments
Questions:
1. List advantages and limitations of Hill Cipher.
2. Describe in which applications this cipher could be used.
3. Read the paper given to you and summarize how is it better than Hill Cipher
Certainly! Below is a similar script and discussion for the Hill Cipher, following the structure and wording you provided for the Vigenere Cipher.

---

# Introduction to Cryptography Lab 2

## Script to encode and decode

```python
import numpy as np

def generate_key_matrix(key, n):
    key_matrix = []
    for char in key:
        key_matrix.append(ord(char) % 65)
    return np.array(key_matrix).reshape(n, n)

def prepare_text(text, n):
    text = text.upper().replace(" ", "")
    while len(text) % n != 0:
        text += 'X'
    return text

def hill_cipher_encrypt(text, key_matrix):
    n = len(key_matrix)
    text = prepare_text(text, n)
    encrypted_text = ""
    for i in range(0, len(text), n):
        block = [ord(char) % 65 for char in text[i:i+n]]
        encrypted_block = np.dot(key_matrix, block) % 26
        encrypted_text += ''.join(chr(encrypted_block[j] + 65) for j in range(n))
    return encrypted_text

def hill_cipher_decrypt(cipher_text, key_matrix):
    n = len(key_matrix)
    det = int(round(np.linalg.det(key_matrix)))
    det_inv = pow(det, -1, 26)
    matrix_minor = np.linalg.inv(key_matrix).T * det
    adjugate = matrix_minor % 26
    key_inverse = (det_inv * adjugate) % 26
    key_inverse = key_inverse.astype(int)
    decrypted_text = ""
    for i in range(0, len(cipher_text), n):
        block = [ord(char) % 65 for char in cipher_text[i:i+n]]
        decrypted_block = np.dot(key_inverse, block) % 26
        decrypted_text += ''.join(chr(decrypted_block[j] + 65) for j in range(n))
    return decrypted_text

key = input("Enter the key (e.g., 'HILL'): ").upper()
n = int(np.sqrt(len(key)))
key_matrix = generate_key_matrix(key, n)
plaintext = input("Enter the Plain Text: ").upper()
encoded_text = hill_cipher_encrypt(plaintext, key_matrix)
decoded_text = hill_cipher_decrypt(encoded_text, key_matrix)
print("Encoded text:", encoded_text)
print("Decoded text:", decoded_text)
```

![[IMG-20250730000528685.png]]

## Questions

### 1. Advantages and Limitations of the Hill Cipher

**Advantages:**
- **Resistant to Frequency Analysis**: Unlike simpler ciphers, the Hill Cipher can resist basic frequency analysis because it encrypts multiple letters at once. This makes it harder for someone to crack the code just by looking at how often certain letters appear.
- **Customizable Key Size**: The key can be of variable size, which means you can make the encryption as complex as you need. The bigger the key, the harder it is to crack.
- **Mathematical Foundation**: The Hill Cipher uses linear algebra for encryption, which gives it a strong mathematical foundation. This makes it robust against certain types of attacks.

**Limitations:**
- **Vulnerable to Known-Plaintext Attacks**: If an intruder gets their hands on both the plaintext and the corresponding cipher text, they can figure out the key matrix. This is a significant weakness.
- **Complexity in Implementation**: The cipher requires a good understanding of linear algebra, making it more complex to implement compared to simpler ciphers.
- **Key Distribution**: The key matrix must be invertible, which limits the choice of keys. Not all matrices will work, so you have to be careful when choosing one.
- **Error Propagation**: A small error in the cipher text can lead to significant errors in the decrypted text. This means that if something goes wrong during encryption, the decrypted message could be way off.

### 2. Applications of the Hill Cipher

The Hill Cipher is great for situations where you need strong security but don't have a lot of computational resources. Here are a few places where it might be useful:
- **Educational Purposes**: It's a good tool for teaching cryptography concepts and linear algebra. Students can learn a lot about how encryption works by studying the Hill Cipher.
- **Simple Secure Communications**: If you're in a low-resource basic project environment where more complex encryption algorithms are not possible, the Hill Cipher can still provide a good level of security.

### 3. Summary of the Paper
- **Modern Ciphers**: These often use more complex mathematical structures and bigger key sizes, making them much harder to crack.
- **Advanced Algorithms**: Techniques like AES (Advanced Encryption Standard) use a combination of substitution and permutation, which provides stronger security.
- **Efficiency**: Modern ciphers are designed to be computationally efficient. This means they can encrypt and decrypt data quickly, even with large datasets.



# References

###### Information
- date: 2025.01.13
- time: 13:12