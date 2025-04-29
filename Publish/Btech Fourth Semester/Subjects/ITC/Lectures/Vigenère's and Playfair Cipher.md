---
Title: Introduction to Cryptography Lecture 4
Status: true
marker:
  - "[[Vigenère's and Playfair Cipher]]"
  - "[[Introduction To Cryptography (ITC)]]"
  - "[[Ciphers]]"
  - "[[Encryption]]"
  - "[[Playfair Cipher]]"
  - "[[Vigenere's cipher]]"
tags: 
Date: 2025.01.13
Time: 09:04
---
Absent in Earlier Lectures :P **ITC Lecture 1**
- Jump to [[#Playfair cipher]]
# Vigenère's Cipher
Vigenère's Cipher is a classical **polyalphabetic substitution cipher** that encrypts text by using a keyword to shift letters cyclically through the alphabet. Unlike simple substitution ciphers (like the Caesar cipher), which use a single shift value throughout the entire message, the Vigenère cipher varies the shift depending on the keyword, making it much more resistant to frequency analysis. This makes the cipher a type of **polyalphabetic cipher**, where multiple cipher alphabets are used.

---
### Key Points:
1. **Encryption**:
    - Use a keyword (e.g., **KEY**) repeated to match the length of the plaintext.
    - Each letter in the plaintext is shifted by the corresponding letter in the keyword, where $A=0$, $B=1$, ..., $Z=25$.
    - Formula: $C_i = (P_i + K_i) \mod 26$, where $P_i$ is the plaintext letter, $K_i$ is the key letter, and $C_i$ is the ciphertext letter.
    - $E_i = (P_i + K_i) \mod 26$
2. **Decryption**:
    - Reverse the process by subtracting the key value.
    - Formula: $P_i = (C_i - K_i + 26) \mod 26$.
    - $D_i = (E_i - K_i + 26) \mod 26$
3. **Example**:
    - **Plaintext**: **HELLO**
    - **Keyword**: **KEY**
    - **Encryption**:
        - Repeat keyword: **KEYKE**
        - Ciphertext: **RIJVS**
4. **Strengths**:
    - More secure than monoalphabetic ciphers, such as the Caesar cipher, because it disguises the letter frequency better.
    - Conceals letter frequency patterns, making cryptanalysis more challenging.
    - The cipher can handle longer messages with greater security if the keyword is long and random.
    - Suitable for simple encryption tasks in pre-modern cryptography.
5. **Weaknesses**:
    - Vulnerable to Kasiski examination or frequency analysis if the keyword is short, repetitive, or used multiple times.
    - If the keyword is discovered or the key length is too short, the cipher can be easily broken using frequency analysis or the known-plaintext attack.
    - The security of Vigenère's Cipher is tied to the secrecy and randomness of the keyword.
    - Requires both the sender and the receiver to share the same key securely, which introduces the challenge of key distribution.
---
### Advantages of Vigenère's Cipher:

- **Resistance to frequency analysis**: By using a keyword to vary shifts, it avoids the simple frequency distribution that characterizes monoalphabetic ciphers.
- **Efficient for short messages**: With the right key, Vigenère can be used for short messages with decent security, especially when the key is random and kept secret.
- **Can handle large alphabets**: This system works with any alphabet, as long as the shifts are mapped correctly.

### Disadvantages of Vigenère's Cipher:

- **Keyword reuse vulnerability**: If the same keyword is reused across multiple messages, patterns will eventually emerge, allowing an attacker to break the cipher.
- **Key length issues**: If the key length is shorter than the message, it may introduce weaknesses, especially in longer messages where the key repeats frequently.
- **Not scalable**: As cryptographic attacks evolve, the Vigenère cipher's security diminishes. Modern cryptographic systems use more complex algorithms that provide stronger protection.

### Additional Benefits:

- The key length can be as long as $26^n$, where $n$ is the number of letters in the message to be encrypted. This means that even a moderately long key can provide a huge number of possible key combinations, making brute-force attacks infeasible.


---
# Questions

## Question1
Encrypt **"AttackAtDawn"** with key **"Lemon"** with vignere's cipher
### Answer 1
The formulae for encryption is
- $E_i = (P_i + K_i) \mod 26$

```python
def vigenere_cipher(text, key):

    encoded_text = []

    # Empty array for encoded text

    key_as_int = [ord(i) for i in key]

    # Convert the key to ascii using ORD Function

    # ord() function returns the ASCII value of the character

    # using for inside a list iterates the key and converts it to ascii value and stores it in the list

    text_as_int = [ord(i) for i in text]

    # get the ordinal for each character in the text and store it in a list

    # Convert the text to ascii using ORD Function

    # ord() function returns the ASCII value of the character

    # using for inside a list iterates the text and converts it to ascii value and stores it in the list

    for i in range(len(text_as_int)):

        # Iterate through the text

        value = (text_as_int[i] + key_as_int[i % len(key)]) % 26

        # calculate the value of encoded key

        encoded_text.append(chr(value + 65))

        # Append 65 to the value to convert into ASCII value

    return ''.join(encoded_text)

  

def inverse_vignere_cipher(encoded_text,key):

    real_text = []

    # Empty array for real text

    key_length = len(key)

    # length of the array stored

    key_as_int=[ord(i) for i in key]

    # Convert the key to ascii using ORD Function

  

    encoded_text_as_int = [ord(i) for i in encoded_text]

    for i in range(len(encoded_text_as_int)):

        value = (encoded_text_as_int[i]-key_as_int[i%len(key)])%26

        # calculate the value of encoded key

  

        real_text.append(chr(value+65))

        # Append 65 to the value to convert into ASCII value

    return ''.join(real_text)

  
  
  

text = "ATTACKATDAWN"

key = "LEMON"

encoded_text = vigenere_cipher(text, key)

decoded_text = inverse_vignere_cipher(encoded_text,key)

print(encoded_text)

print(decoded_text)
```

---
# Playfair cipher
The **Playfair Cipher** is a **digraph substitution cipher** that encrypts pairs of letters (bigrams) in the plaintext rather than single letters. It was invented by Charles Wheatstone in 1854, but it was named after Lord Playfair, who promoted its use in the British military.

The Playfair Cipher is more secure than the simple Caesar cipher or monoalphabetic substitution ciphers because it encrypts pairs of letters, making frequency analysis more difficult.
### Key Points of the Playfair Cipher:

1. **Key Square**:
    - The encryption process begins by creating a 5x5 matrix (also called a "key square") that contains 25 letters. Usually, the letters **A-Z** are used, but one letter (commonly **J**) is omitted to fit the 26 letters into the 25-space matrix.
    - The matrix is filled with the key (the keyword provided by the user) followed by the remaining unused letters of the alphabet in order.
    For example, let's take the keyword **"KEYWORD"**. After removing duplicate letters, the matrix would look like this:
    
    ```
    K  E  Y  W  O
    R  D  A  B  C
    F  G  H  I  L
    M  N  P  Q  S
    T  U  V  X  Z
    ```
    
2. **Preprocessing the Plaintext**:
    - The plaintext message is divided into pairs of letters (digraphs). If there is an odd number of letters, a filler letter (usually **X**) is added to the last letter.
    - If a pair of letters in the plaintext is the same (e.g., "LL"), an **X** is inserted between them to make them different (e.g., "LX" and "LX").
3. **Encryption Rules**: The encryption of each pair is done according to the following rules:
    - **Rule 1: Same Row**: If the two letters of the pair appear in the same row of the key square, each letter is replaced with the letter immediately to its right. If a letter is in the last column, it wraps around to the first column of the same row.
        For example:
        - Pair: **"HE"**
        - H and E are in the first row, so replace them with the letters immediately to their right: **"EK"**.
    - **Rule 2: Same Column**: If the two letters of the pair appear in the same column, each letter is replaced by the letter immediately below it. If a letter is in the last row, it wraps around to the top row of the same column.
        For example:
        - Pair: **"HE"**
        - If "H" and "E" were in the same column, they would be replaced with the letters below them.
    - **Rule 3: Rectangle**: If the two letters of the pair are not in the same row or column (i.e., they form a rectangle), each letter is replaced by the letter on the same row but in the opposite column.
        
        For example:
        
        - Pair: **"HE"**
        - If H is at (1,1) and E is at (1,2), and they form a rectangle, the letters are replaced by letters from the other corners of the rectangle.
4. **Decryption**:
    
    - The decryption process is essentially the reverse of encryption. The same key square is used, but instead of moving to the right or down, the letters are moved to the left or up according to the same rules.
    - If the pair was in the same row, each letter is replaced by the letter immediately to its left. If the pair was in the same column, each letter is replaced by the letter immediately above it.

### Example:
Let's walk through an example of encrypting a message using the Playfair Cipher:
**Plaintext**: **"HELLO"**
1. **Preprocessing**:
    - Split into pairs: **"HE"**, **"LL"**, **"O"**. Add a filler "X" to the last letter: **"OX"**.
    - Now we have: **"HE"**, **"LX"**, **"OX"**.
2. **Create the Key Square** (using keyword "KEYWORD"):
    ```
    K  E  Y  W  O
    R  D  A  B  C
    F  G  H  I  L
    M  N  P  Q  S
    T  U  V  X  Z
    ```
3. **Encryption**:
    - For the pair **"HE"**:
        - "H" and "E" are in the same row (third row), so replace them with the letters immediately to their right: **"EI"**.
    - For the pair **"LX"**:
        - "L" and "X" are in the same column (fifth column), so replace them with the letters immediately below them: **"ZV"**.
    - For the pair **"OX"**:
        - "O" and "X" are in different rows and columns, so form a rectangle: replace "O" with "W" and "X" with "Z": **"WZ"**.
4. **Ciphertext**: **"EI ZV WZ"**.
    

### Advantages of Playfair Cipher:

- **Stronger than monoalphabetic ciphers**: It uses digraphs instead of single letters, making it harder to analyze using frequency analysis.
- **Relatively simple**: While more complex than basic ciphers, it's still relatively easy to implement and understand.

### Disadvantages:

- **Vulnerable to cryptanalysis**: Though it provides more security than simple ciphers, the Playfair cipher is still vulnerable to attacks like **frequency analysis** (especially if the keyword is short or easily guessable).
- **Limited to 25 letters**: Since the key square is 5x5, only 25 letters can be used, leaving out one letter (typically **J**).
- **Requires both sender and receiver to share the same key**: Key distribution is a major issue, especially if the key is kept secret.

### Summary:

The **Playfair Cipher** is a **polyalphabetic** cipher that encrypts pairs of letters, providing greater security than simpler ciphers like the Caesar Cipher. While it is an interesting historical cipher, it has been largely superseded by modern cryptographic methods.
# References

###### Information

- date: 2025.01.13
- time: 09:04
- Continued to [[Transposition Cipher]]

---

This version includes more detailed explanations of the cipher's structure, its advantages and weaknesses, and a more comprehensive overview of the polyalphabetic nature of the cipher.