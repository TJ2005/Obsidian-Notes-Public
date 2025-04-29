---
Title: "Introduction to Cryptography Lab 2 Playfair Cipher"
Status: 
marker: 
tags: 
Date: "2025.02.17"
Time: "13:11"
---

# Introduction to Cryptography Lab 2

## Script to encode and decode

```python
def generate_table(key):
    key = key.upper()
    key_table = []
    for char in key:
        if char not in key_table and char.isalpha():
            key_table.append(char)
    for char in "ABCDEFGHIKLMNOPQRSTUVWXYZ":
        if char not in key_table:
            key_table.append(char)
    return [key_table[i:i + 5] for i in range(0, 25, 5)]

def prepare_text(text):
    text = text.upper().replace("J", "I")
    text = ''.join(filter(str.isalpha, text))
    prepared_text = []
    i = 0
    while i < len(text):
        if i + 1 < len(text) and text[i] != text[i + 1]:
            prepared_text.append(text[i] + text[i + 1])
            i += 2
        elif i + 1 < len(text) and text[i] == text[i + 1]:
            prepared_text.append(text[i] + 'X')
            i += 1
        else:
            prepared_text.append(text[i] + 'X')
            i += 1
    return prepared_text

def find_position(table, char):
    for i, row in enumerate(table):
        if char in row:
            return (i, row.index(char))
    return None

def playfair_cipher(text, key):
    table = generate_table(key)
    prepared_text = prepare_text(text)
    encoded_text = []
    for pair in prepared_text:
        row1, col1 = find_position(table, pair[0])
        row2, col2 = find_position(table, pair[1])
        if row1 == row2:
            encoded_text.append(table[row1][(col1 + 1) % 5] + table[row2][(col2 + 1) % 5])
        elif col1 == col2:
            encoded_text.append(table[(row1 + 1) % 5][col1] + table[(row2 + 1) % 5][col2])
        else:
            encoded_text.append(table[row1][col2] + table[row2][col1])
    return ''.join(encoded_text)

def inverse_playfair_cipher(encoded_text, key):
    table = generate_table(key)
    prepared_text = [encoded_text[i:i + 2] for i in range(0, len(encoded_text), 2)]
    decoded_text = []
    for pair in prepared_text:
        row1, col1 = find_position(table, pair[0])
        row2, col2 = find_position(table, pair[1])
        if row1 == row2:
            decoded_text.append(table[row1][(col1 - 1) % 5] + table[row2][(col2 - 1) % 5])
        elif col1 == col2:
            decoded_text.append(table[(row1 - 1) % 5][col1] + table[(row2 - 1) % 5][col2])
        else:
            decoded_text.append(table[row1][col2] + table[row2][col1])
    return ''.join(decoded_text)

key = input("Enter the key: ").upper()
plaintext = input("Enter the Plain Text: ").upper()
encoded_text = playfair_cipher(plaintext, key)
decoded_text = inverse_playfair_cipher(encoded_text, key)
print("Encoded text:", encoded_text)
print("Decoded text:", decoded_text)
```

## Questions

1. Is the 19th century - Playfair Cipher still worthy? Justify?
   When the key and message are short, the Playfair Cipher is easy to be brute-forced. The iterations required will be $25!$ (factorial) due to the permutations of the 5x5 key table. To solve this problem, we have to make the message longer and the key too. However, with longer text phrases, due to the nature of language, words will be repetitive. And that leads to easy giveaways.

2. What are the common types of attacks on the Playfair Cipher?
   - **Frequency Analysis**: By analyzing the frequency of digraphs (pairs of letters) in the cipher text, it's possible to identify repeating patterns that correspond to the structure of the key table.
   - **Pattern Recognition**: The Playfair Cipher preserves the pairing of letters, which can reveal patterns in the cipher text that correspond to common digraphs in the plaintext.
   - **Known-Plaintext Attack**: If an attacker has access to both the plaintext and the corresponding cipher text, they can deduce the key table by analyzing the transformations.

3. Discuss the impact of the key length on the security of the Playfair cipher. Why does a longer key generally provide better security?
   The key length being longer means the number of possible key tables increases. With the increase in length, the iterations required will be $25!$ (factorial). Thus, exponentially increasing the iterations required.

4. What is the difference between the autokey method and the keyword method of the Playfair Cipher?
   - **Keyword Method**: The key is a single keyword that is used to fill the 5x5 table, followed by the remaining letters of the alphabet (excluding 'J'). This method is straightforward but can be less secure if the keyword is short.
   - **Autokey Method**: The key is generated dynamically based on the plaintext itself, making the encryption more resistant to frequency analysis. However, this method is more complex to implement and use.

# References

###### Information
- date: 2025.01.13
- time: 13:12

---

# References


###### Information
- date: 2025.02.17
- time: 13:11