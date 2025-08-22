---
Title: AES
Status: 
marker:
  - "[[Introduction To Cryptography (ITC)]]"
  - "[[ITC Unit 3]]"
tags:
  - BTech
  - Note
Date: 2025.05.03
Time: 15:04
---
# AES
In 1997, NIST Started looking for replacement of DES. It would be called Advanced Encryption System. NIST Took 15 out of the 21 received algorithm had met the requirements and been selected as candidates. 

AES Works with blocks of sizes of bits 128, 192, 256 bits. 

```mermaid

```

## State
AES Uses several where each round is made of several stages. Data blocks are transformed at each stage. AES Uses the term *Data Block* To call the inputs and outputs provided and received from each ***State***. We can use upper case letter **T** to represent temporary state. These states are made of **16 Bytes** but normally they are called matrices $4 \times 4$ bytes matrix. 

## Transformations
### Substitution
In aes we use substitution but the mechanism is different than DES. 
- First substitution is done for each byte.
- Second only one table is used for transformation of every byte, which means two bytes are the same, the transformation is also the same.
- The third step  is to use a table lookup in the GF( $2^8$ )
#### S Box
There is 


References


###### Information
- date: 2025.05.03
- time: 15:04