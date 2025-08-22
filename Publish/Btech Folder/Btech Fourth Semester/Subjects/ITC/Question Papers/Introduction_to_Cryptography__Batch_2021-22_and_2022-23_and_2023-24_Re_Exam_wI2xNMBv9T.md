---
Title: Introduction_to_Cryptography__Batch_2021-22_and_2022-23_and_2023-24_Re_Exam_wI2xNMBv9T
Status: true
marker:
  - "[[Introduction To Cryptography (ITC)]]"
tags:
  - "#QuestionPaper"
  - BTech
Date: 2025.04.19
Time: 15:52
---
C# Introduction_to_Cryptography__Batch_2021-22_and_2022-23_and_2023-24_Re_Exam_wI2xNMBv9T

> [!Questiin Paper]
> **Title**: Introduction_to_Cryptography__Batch_2021-22_and_2022-23_and_2023-24_Re_Exam_wI2xNMBv9T
> 
> **File Link ** : [[IMG-20250730000529013.pdf]]




# Questions 1 ( Compulsory )

## Question A

**YXTJTVVBJJ**

### The Encryption Process

1. First encryption: Vigenère Cipher with key "RIVER"
2. Second encryption: Permutation Cipher with key:

$$\pi = \begin{pmatrix}  
1 & 2 & 3 & 4 & 5 \\  
5 & 4 & 2 & 3 & 1  
\end{pmatrix}$$

### Step 1: Reverse the Permutation Cipher

To decrypt, we need to apply the inverse permutation first. The given permutation maps:

- Position 1 → 5
    
- Position 2 → 4
    
- Position 3 → 2
    
- Position 4 → 3
    
- Position 5 → 1
    

The inverse permutation is:

$$\pi^{-1} = \begin{pmatrix}  
1 & 2 & 3 & 4 & 5 \\  
5 & 3 & 4 & 2 & 1  
\end{pmatrix}$$

Let's split the ciphertext into blocks of 5 characters:

- Block 1: YXTJT
- Block 2: VVBJJ

Applying the inverse permutation:
### Block 1: YXTJT

- Position 1 (from position 5) → T
    
- Position 2 (from position 3) → T
    
- Position 3 (from position 4) → J
    
- Position 4 (from position 2) → X
    
- Position 5 (from position 1) → Y
    

Result: TTJXY

### Block 2: VVBJJ

- Position 1 (from position 5) → J
    
- Position 2 (from position 3) → B
    
- Position 3 (from position 4) → J
    
- Position 4 (from position 2) → V
    
- Position 5 (from position 1) → V
    

Result: JBJVV

Combined result after reversing the permutation: **TTJXYJBJVV**

### Step 2: Reverse the Vigenère Cipher

Now we need to decrypt the Vigenère cipher using the key "RIVER".

For Vigenère decryption, we use the formula:  
$P = (C - K + 26) \mod 26$

Where:

- $P$ is the plaintext letter (as a number from 0-25)
    
- $C$ is the ciphertext letter (as a number from 0-25)
    
- $K$ is the key letter (as a number from 0-25)
    

The key "RIVER" repeats to match the length of the ciphertext: RIVERRIVER

|Position|Ciphertext|Key|C (0-25)|K (0-25)|P = (C-K+26)%26|Plaintext|
|---|---|---|---|---|---|---|
|1|T|R|19|17|2|C|
|2|T|I|19|8|11|L|
|3|J|V|9|21|14|O|
|4|X|E|23|4|19|T|
|5|Y|R|24|17|7|H|
|6|J|R|9|17|18|S|
|7|B|I|1|8|19|T|
|8|J|V|9|21|14|O|
|9|V|E|21|4|17|R|
|10|V|R|21|17|4|E|

### Final Result

The decrypted plaintext is: **CLOTHSTORE**

---

Answer from Perplexity: [pplx.ai/share](https://www.perplexity.ai/search/pplx.ai/share)

## Question B

# References


## Information
- date: 2025.04.19
- time: 15:52