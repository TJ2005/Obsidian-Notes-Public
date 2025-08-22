---
Title: Introduction to Cryptography Lab 7
Status: true
marker:
  - "[[Introduction To Cryptography (ITC)]]"
  - "[[Cryptography]]"
tags:
  - "#BTech"
Date: 2025.03.29
Time: 11:39
---
# DES
RSA is an algorithm used to encrypt and decrypt messages. It is an asymmetric cryptographic algorithm that uses a pair of keys: a public key for encryption and a private key for decryption. The security of RSA relies on the difficulty of factoring large composite numbers.

## Code
```python
import dns.resolver

from cryptography.fernet import Fernet  # type: ignore

# Generate a key for encryption

key = Fernet.generate_key()

cipher_suite = Fernet(key)

# Save the key to a file (optional, to reuse later)

with open("secret.key", "wb") as key_file:

    key_file.write(key)

# Function to resolve a domain name

def query_dns(domain):

    try:

        result = dns.resolver.resolve(domain, 'A')

        ip_addresses = [ip.address for ip in result]

        return ', '.join(ip_addresses)

    except Exception as e:

        return str(e)

# Encrypt the DNS response

def encrypt_dns_data(data):

    encrypted_data = cipher_suite.encrypt(data.encode())

    return encrypted_data

# Decrypt the DNS response

def decrypt_dns_data(encrypted_data):

    decrypted_data = cipher_suite.decrypt(encrypted_data).decode()

    return decrypted_data

# Example usage

if __name__ == "__main__":

    domain = "google.com"

    dns_response = query_dns(domain)

    print("Original DNS Response:", dns_response)

    encrypted_response = encrypt_dns_data(dns_response)

    print("Encrypted Response:", encrypted_response)

    decrypted_response = decrypt_dns_data(encrypted_response)

    print("Decrypted Response:", decrypted_response)
   
```

**Output:**
```bash
Original DNS Response: 142.250.192.46
Encrypted Response: b'gAAAAABn4teV8MHOkc7xKiNDzmm6EC7GM579zsnptCXyH4X3Pmx7dheqf1vRwhy1uQjeQVAB1cPOp7iNAPZr
Decrypted Response: 142.250.192.46
```


## Questions
**. Significance of Initial Permutation (IP) and Final Permutation (FP) in DES:**

- **Initial Permutation (IP)**: The IP shuffles the order of the bits in the plaintext block before encryption starts. Although this permutation doesn’t add any cryptographic strength, it ensures a fixed order of input to the subsequent rounds, which simplifies hardware implementation.
- **Final Permutation (FP)**: The FP is the inverse operation of the IP. It reorders the bits of the ciphertext back to their original order after all encryption rounds are complete. Like IP, FP mainly assists hardware implementation without contributing to the algorithm's security.

**2. Key Whitening in DES-based Algorithms:**

Key whitening is a technique used to increase security by XORing additional keys with the plaintext before encryption and/or with the ciphertext after encryption. This:

- Prevents certain cryptanalytic attacks (e.g., differential and linear attacks) by adding more complexity to the data manipulation.
- Extends the effective key length beyond the original DES limit of 56 bits, making brute-force attacks much harder.

**3. Handling Encryption of Messages Longer than 64 Bits in DES:**

DES operates on 64-bit blocks of plaintext. If the message exceeds 64 bits:

- **Block Chaining**: DES splits the message into multiple 64-bit blocks and encrypts them individually.
- **Padding**: If the last block is smaller than 64 bits, padding is added to make it a full 64-bit block. Padding schemes like PKCS#7 are commonly used.
- DES modes of operation (e.g., ECB, CBC, etc.) determine how these blocks are encrypted and linked to each other.

**4. Advantages of CBC (Cipher Block Chaining) Mode Over ECB:**

- **Improved Security**: CBC introduces an Initialization Vector (IV) that makes each ciphertext block dependent on the previous one. This ensures identical plaintext blocks produce different ciphertexts, making patterns in the plaintext less detectable.
- **Resilience to Patterns**: Unlike ECB, CBC avoids the vulnerability of repetitive ciphertext patterns that could expose plaintext structure.

###### Information
- date: 2025.03.29
- time: 11:39