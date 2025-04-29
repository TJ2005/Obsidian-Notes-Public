---
Title: Introduction to Cryptography Lab 2
Status: 
marker:
  - "[[Programming]]"
tags: 
Date: 2025.01.13
Time: 13:12
---
# Introduction to Cryptography Lab 2

## Script to encode and decode
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

        if text_as_int[i] == 32:

            # check if the text is a space

  

            encoded_text.append(" ")

            # append the space to the encoded text

            continue

        else:

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

        if encoded_text_as_int[i] == 32:

            # check if the encoded text is a space

            real_text.append(" ")

            # append the space to the real text

            continue

        else:

            value = (encoded_text_as_int[i]-key_as_int[i%len(key)])%26

            # calculate the value of encoded key

  

            real_text.append(chr(value+65))

            # Append 65 to the value to convert into ASCII value

    return ''.join(real_text)

key=input("Enter the key: ").upper()

plaintext = input("Enter the Plain Text: ").upper()

encoded_text = vigenere_cipher(plaintext, key)

decoded_text = inverse_vignere_cipher(encoded_text,key)

print("encoded text:",encoded_text)

print("decoded text:",decoded_text)
```
## Questions
1.      Is the 16th century - Vigenere Cipher still worthy? Justify?
			When the key and message are short the vigenere's cipher is easy to be bruteforced. The iterations required will be $26^{length(key)}$.
			To solve this problem we have to make the message longer and key too.  However with longer text phrases due to the nature of language words will be repetitive. And that leads to easy giveaways.
2.      What is the common types of attacks on Vigenere Cipher?
		- Frequency Analysing : By analyzing the frequency of letters in the cipher text, it's possible to identify repeating patterns that correspond to the length of the key.
		- **Kasiski Examination**: This method involves finding repeated sequences of letters in the cipher text. The distance between these repetitions can help deduce the key length.
		- **Babbage's Method**: Similar to the Kasiski Examination, this method also looks for repeated sequences. Babbage’s insight was to note that the distances between these sequences are often multiples of the key length.
3.      Discuss the impact of the key length on the security of the Vigenère cipher. Why does a longer key generally provide better security? 
			The key length being longer means the length increases. With the increase in length The iterations required will be $26^{length(key)}$.
			Thus exponentially increasing the  iterations required. 
4.      What is difference of autokey method and keyword method of Vigenere Cipher?
		-  **Key Generation**: The key is a single keyword that is repeated to match the length of the plaintext. For example, if the keyword is "KEY" and the plaintext is "HELLO", the key would be repeated as "KEYKE".
		- **Encryption/Decryption**: Each letter of the plaintext is shifted according to the corresponding letter of the repeated keyword. This can make the encryption more secure than a simple Caesar cipher, but it is still vulnerable to frequency analysis attacks.





# References


###### Information
- date: 2025.01.13
- time: 13:12