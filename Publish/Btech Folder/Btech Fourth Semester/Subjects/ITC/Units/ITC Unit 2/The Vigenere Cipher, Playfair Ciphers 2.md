---
Title: The Vigenere Cipher, Playfair Ciphers
Status: 
marker:
  - "[[Introduction To Cryptography (ITC)]]"
  - "[[ITC Unit 2]]"
tags:
  - BTech
  - Note
Date: 2025.04.19
Time: 12:34
---
# The Vigenere Cipher, Playfair Ciphers

> [!Related Notes]
>
> - [[Shift Ciphers, Affine Ciphers]]
> - [[Substitution Ciphers, Transposition Ciphers]]
> - [[Perfectly secret encryption, one time pad and Shannon's theorem]]

## Polyalphabetic Ciphers

Polyalphabetic ciphers were developed to address the weaknesses of monoalphabetic ciphers like the [[Shift Ciphers, Affine Ciphers|shift and affine ciphers]]. In monoalphabetic ciphers, each character is substituted by a single character, making them vulnerable to frequency analysis.

The goal of polyalphabetic ciphers is to make cryptanalysis more difficult by having each plaintext character replaced by more than one possible ciphertext character, depending on its position in the text.

## The Vigenère Cipher

The Vigenère cipher is one of the most well-known polyalphabetic substitution ciphers. It uses a keyword to determine which shift cipher to apply to each letter of the plaintext.

### Vigenère Table

The Vigenère cipher uses a 26×26 table of characters called the Vigenère square or Vigenère table:

```
   | A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
---+----------------------------------------------------
 A | A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
 B | B C D E F G H I J K L M N O P Q R S T U V W X Y Z A
 C | C D E F G H I J K L M N O P Q R S T U V W X Y Z A B
 D | D E F G H I J K L M N O P Q R S T U V W X Y Z A B C
 E | E F G H I J K L M N O P Q R S T U V W X Y Z A B C D
 F | F G H I J K L M N O P Q R S T U V W X Y Z A B C D E
 G | G H I J K L M N O P Q R S T U V W X Y Z A B C D E F
 H | H I J K L M N O P Q R S T U V W X Y Z A B C D E F G
 I | I J K L M N O P Q R S T U V W X Y Z A B C D E F G H
 J | J K L M N O P Q R S T U V W X Y Z A B C D E F G H I
 K | K L M N O P Q R S T U V W X Y Z A B C D E F G H I J
 L | L M N O P Q R S T U V W X Y Z A B C D E F G H I J K
 M | M N O P Q R S T U V W X Y Z A B C D E F G H I J K L
```


### Encryption Process

1. Choose a keyword (e.g., "INFOSEC")
2. Repeat the keyword to match the length of the plaintext
3. For each letter in the plaintext:
    - Find the row corresponding to the keyword letter
    - Find the column corresponding to the plaintext letter
    - The intersection gives the ciphertext letter

### Example

Message: "SEE ME IN MALL"
Keyword: "INFOSEC"
 
First, align the keyword with the plaintext:

```
S E E M E I N M A L L
I N F O S E C I N F O
```

Then encrypt each letter using the Vigenère table:

```
S + I = A (row I, column S)
E + N = R (row N, column E)
E + F = J (row F, column E)
...and so on
```

Resulting in ciphertext: "ARJAWMPUNQZ"

### Mathematical Representation

The Vigenère cipher can be expressed mathematically:

For encryption:
$E_i = (P_i + K_i) \mod 26$

For decryption:
$D_i = (E_i - K_i + 26) \mod 26$

Where:

- $P_i$ is the numerical value of the ith plaintext letter (A=0, B=1, etc.)
- $K_i$ is the numerical value of the ith letter in the key (repeated as necessary)
- $E_i$ is the numerical value of the ith ciphertext letter


### Security of the Vigenère Cipher

The Vigenère cipher is significantly more secure than monoalphabetic ciphers because:

- Each letter can be encrypted to multiple different letters depending on its position
- Letter frequency analysis is much more difficult
- The longer the keyword, the more secure the cipher

However, it can still be broken using techniques like the Kasiski examination or the Friedman test, which can determine the length of the keyword.

## Playfair Cipher

The Playfair cipher is another polyalphabetic substitution cipher that encrypts pairs of letters (digraphs) instead of single letters.

### Key Table Construction

1. Create a 5×5 grid of letters based on a keyword
2. Fill the grid with the letters of the keyword (removing duplicates)
3. Fill the remaining spaces with the rest of the alphabet (usually combining I and J)

Example using the keyword "SECURITY":

```
S E C U R
I T Y A B
D F G H K
L M N O P
Q V W X Z
```


### Encryption Rules

Before encryption, the plaintext is divided into pairs of letters. If a pair would contain the same letter twice, a filler letter (usually 'X') is inserted. If the message has an odd number of letters, a filler letter is added at the end.

For each pair of letters:

1. If the two letters are in the same row, replace each with the letter to its right (wrapping around to the beginning of the row if necessary)
2. If the two letters are in the same column, replace each with the letter below it (wrapping around to the top of the column if necessary)
3. If the two letters form a rectangle, replace each with the letter at the same row but in the column of the other letter

### Example

Message: "HELLOWORLD"
After preparing: "HE LX LO WO RL DX" (X inserted between double L, and at the end)

Using the key table above:

- HE: H and E form a rectangle → FU
- LX: L and X form a rectangle → OQ
- LO: L and O form a rectangle → MP
- WO: W and O form a rectangle → XN
- RL: R and L form a rectangle → SP
- DX: D and X form a rectangle → HZ

Resulting in ciphertext: "FUOQMPXNSPHZ"

### Security of the Playfair Cipher

The Playfair cipher is more secure than simple substitution ciphers because:

- It encrypts digraphs rather than single letters
- There are 26² = 676 possible digraphs compared to just 26 letters
- Frequency analysis is much more complex

However, it still has weaknesses:

- Certain patterns can emerge in the ciphertext
- The most common digraphs in English (TH, HE, AN, etc.) can be identified
- Modern computing power makes brute force attacks feasible


## Relationship to One-Time Pad

The Vigenère cipher can be seen as a precursor to the [[Perfectly secret encryption, one time pad and Shannon's theorem|one-time pad]]. If the key in a Vigenère cipher is:

1. As long as the message
2. Truly random
3. Used only once

Then it becomes a one-time pad, which is theoretically unbreakable. The Vigenère cipher with a repeating keyword falls short of this ideal, making it vulnerable to cryptanalysis.

Both the Vigenère and Playfair ciphers represent significant advancements in the evolution of cryptography, addressing weaknesses in earlier [[Shift Ciphers, Affine Ciphers|shift and affine ciphers]] and laying groundwork for modern [[Substitution Ciphers, Transposition Ciphers|substitution techniques]].



# References


###### Information
- date: 2025.04.19
- time: 12:34