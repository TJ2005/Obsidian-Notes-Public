---
Title: Introduction to Cryptography Computer Lab 1
Status: 
marker:
  - "[[Cryptography]]"
tags: 
Date: 2025.01.13
Time: 12:19
---
# Introduction to Cryptography Computer Lab 1


---

**Academic Year**: 2024-25  
**Programme**: BTECH CSE Cybersecurity  
**Year**: 2nd  
**Semester**: IV  
**Student Name**: Tejas Sahoo  
**Batch**: K2  
**Roll No**: K057  

---

### **Experiment 1: Caesar Cipher**

#### **Aim**:

To implement shift ciphers and to study various terms related to cryptography.

---

#### **Learning Outcomes**:

After completion of this experiment, the student should be able to:

1. Describe basic symmetric key encryption and decryption process.
2. Understand the working of substitution ciphers.
3. State limitations of shift ciphers.
4. Implement brute force attack.

---

#### **Theory**:

Following are the basic terms related to cryptography:

- **Plain Text**: The original information.
- **Ciphertext**: Unintelligible gibberish data. It is the output of the encryption process.
- **Encryption**: The process of converting ordinary information (plaintext) into unintelligible gibberish (ciphertext).
- **Decryption**: The reverse process of moving from the unintelligible ciphertext back to plaintext.
- **Cipher**: A pair of algorithms that create the encryption and the reversing decryption.
- **Key**: A secret parameter that controls the operation of the cryptographic algorithm.

In cryptography, a **Caesar cipher** (also known as Caesar's cipher or shift cipher) is one of the simplest and most widely known encryption techniques. It is a type of substitution cipher where each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet. The method is named after Julius Caesar, who used it in his private correspondence.

The encryption can also be represented using modular arithmetic by transforming the letters into numbers: A = 0, B = 1, ..., Z = 25. Encryption of a letter by a shift n can be described mathematically as:

Encrypted character=(Original character+n)mod  26\text{Encrypted character} = (\text{Original character} + n) \mod 26

Decryption is performed similarly.

---

#### **Example**:

Plaintext: `HELLO WORLD`  
Key: 3  
Ciphertext: `KHOOR ZRUOG`

---

### **Procedure**:

**Part A: Encryption**

1. Accept key and plaintext from the user.
2. Encrypt plaintext using substitution cipher.
3. Output ciphertext.

**Part B: Decryption**

1. Accept key and ciphertext from the user.
2. Decrypt ciphertext using substitution cipher.
3. Output plaintext.

**Part C: Brute Force Attack**

1. Accept ciphertext from the user.
2. Decrypt ciphertext using substitution cipher.
3. Output plaintext for all possible keys.

---

### **Algorithm for Caesar Cipher**:

**Encryption**:

1. **Input**: Plaintext message, shift value (key) kk.
2. **Process**:
    - For each character in the plaintext:
        - If the character is a letter, shift it by kk positions forward in the alphabet.
        - If the shift exceeds 'Z' or 'z', wrap around to the beginning.
        - Leave non-alphabet characters unchanged.
3. **Output**: Ciphertext message.

**Decryption**:

1. **Input**: Ciphertext message, same shift value kk.
2. **Process**:
    - For each character in the ciphertext:
        - If the character is a letter, shift it by kk positions backward in the alphabet.
        - If the shift goes below 'A' or 'a', wrap around to the end.
        - Leave non-alphabet characters unchanged.
3. **Output**: Decrypted plaintext message.

---

### **Code**:

#### **Encryption Code**:
```python
# Encryption

text = input("Enter the Plain Text: ")

  

# Ensuring the key is an integer

while True:

    try:

        key = int(input("Enter the Key: "))

        break  # Break the loop if input is valid

    except ValueError:

        print("Invalid input. Please enter an integer for the key.")

  

alphabet_upper = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"

alphabet_lower = "abcdefghijklmnopqrstuvwxyz"

  

ciphertext = ""

for char in text:

    if char.isupper():

        index = alphabet_upper.index(char)

        ciphertext += alphabet_upper[(index + key) % 26]

    elif char.islower():

        index = alphabet_lower.index(char)

        ciphertext += alphabet_lower[(index + key) % 26]

    else:

        ciphertext += char  # If the character is not a letter, keep it unchanged

  

print("Ciphertext:", ciphertext)
```


![[IMG-20250730000529025.png]]
#### **Decryption Code**:
```python
# Decryption
text = input("Enter the Ciphertext: ")
key = int(input("Enter the Key: "))

alphabet_upper = "ABCDEFGHIJKLMNOPQRSTUVWXYZ "
alphabet_lower = "abcdefghijklmnopqrstuvwxyz "

plaintext = ""
for char in text:
    if char.isupper():
        index = alphabet_upper.index(char)
        plaintext += alphabet_upper[(index - key) % 26]
    elif char.islower():
        index = alphabet_lower.index(char)
        plaintext += alphabet_lower[(index - key) % 26]
    else:
        plaintext += char

print("Plaintext:", plaintext)
```
![[IMG-20250730000551756.png]]
---

### **Questions**:

1. **Describe the characteristics of a secure cryptographic algorithm.**
    
    - **Strength against attacks**: Resistant to known cryptanalysis techniques (e.g., brute force, differential, and linear attacks).
    - **Large key space**: A sufficiently large key size to make brute-force attacks impractical.
    - **Randomness**: Keys and ciphertext should be random and unpredictable.
    - **Confusion and Diffusion**: The encryption process should mix the plaintext (confusion) and spread the plaintext over the ciphertext (diffusion).
    - **Efficiency**: The algorithm should perform encryption and decryption efficiently on available hardware and software.
    - **Resistance to known attacks**: Proven to withstand attacks from methods like side-channel attacks or chosen-ciphertext attacks.
2. **What are some common tools used for brute force attacks, and how do they function?**
    
    - **Hashcat**: A password cracking tool that uses various algorithms for brute force and dictionary-based attacks.
    - **John the Ripper**: A widely-used password cracking software that can attempt brute force and dictionary attacks.
    - **Aircrack-ng**: Specifically designed for wireless network password cracking, it uses brute force methods to decipher Wi-Fi keys.
    - **Function**: These tools systematically test all possible combinations of passwords or encryption keys, with the goal of finding the correct one by trying each possibility.
3. **How can frequency distribution analysis be used to identify patterns in ciphertext?**
    
    - Frequency analysis examines the frequency of symbols or groups of symbols in ciphertext.
    - In many ciphers (like Caesar cipher), common letters or groups in plaintext (e.g., "E" in English) appear with predictable frequencies in the ciphertext.
    - By comparing the distribution of characters in the ciphertext to the typical distribution in the language of the plaintext, attackers can guess potential letter mappings, aiding in cryptanalysis.
4. **What are the key characteristics of a brute force attack, and how does it differ from a dictionary attack?**
    
    - **Brute Force Attack**: Tries every possible combination of characters until the correct one is found. It can crack any password, given enough time.
    - **Dictionary Attack**: Uses a predefined list (dictionary) of likely passwords (e.g., common words, phrases, or combinations). It’s faster than brute force but limited to the dictionary’s words.
5. **How can statistical analysis be used to detect anomalies in network traffic that may indicate a brute force attack?**
    
    - Statistical analysis monitors network traffic for irregular patterns, such as:
        - A sudden increase in login attempts or request rates from a single IP address.
        - Frequent failed login attempts, which are common during brute force attacks.
        - Unusual patterns in traffic, such as repetitive or systematic queries to a login interface.
    - Anomalies like these can be flagged as potential brute force attempts, prompting further investigation or defensive actions.

---




# References


###### Information
- date: 2025.01.13
- time: 12:19