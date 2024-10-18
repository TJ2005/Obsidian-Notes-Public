---
Title: Digital Logic Design Lecture 7
Status: 
marker: 
tags: 
Date: 2024.08.06
Time: 13:12
---
# Digital Logic Design Lecture 7

# Main note

 ## Hexadecimal to Octal Conversion

To convert a hexadecimal number to an octal number, follow these steps:
1. Convert the hexadecimal number to its binary equivalent.
2. Group the binary digits into sets of three, starting from the right.
3. Convert each group of three binary digits to its octal equivalent.

### Example: Convert $(2F9A)_{16}$ to Octal

**Solution:**

1. Convert the hexadecimal number to binary:
   - $2_{16} = 0010_{2}$
   - $F_{16} = 1111_{2}$
   - $9_{16} = 1001_{2}$
   - $A_{16} = 1010_{2}$

   So, $(2F9A)_{16} = (0010111110011010)_{2}$

2. Group the binary digits into sets of three:
   - $001 \ 011 \ 111 \ 001 \ 101 \ 0$

3. Convert each group to octal:
   - $001_2 = 1_8$
   - $011_2 = 3_8$
   - $111_2 = 7_8$
   - $001_2 = 1_8$
   - $101_2 = 5_8$

   So, $(0010111110011010)_{2} = (13715)_{8}$

Therefore,

$$
(2F9A)_{16} = (13715)_{8}
$$

## Octal to Hexadecimal Conversion

To convert an octal number to a hexadecimal number, follow these steps:
1. Convert the octal number to its binary equivalent.
2. Group the binary digits into sets of four, starting from the right.
3. Convert each group of four binary digits to its hexadecimal equivalent.

### Example: Convert $(13715)_{8}$ to Hexadecimal

**Solution:**

1. Convert the octal number to binary:
   - $1_{8} = 001_{2}$
   - $3_{8} = 011_{2}$
   - $7_{8} = 111_{2}$
   - $1_{8} = 001_{2}$
   - $5_{8} = 101_{2}$

   So, $(13715)_{8} = (001011111001101)_{2}$

2. Group the binary digits into sets of four:
   - $0001 \ 0111 \ 1100 \ 1101$

3. Convert each group to hexadecimal:
   - $0001_2 = 1_{16}$
   - $0111_2 = 7_{16}$
   - $1100_2 = C_{16}$
   - $1101_2 = D_{16}$

   So, $(0001011111001101)_{2} = (17CD)_{16}$

Therefore,

$$
(13715)_{8} = (17CD)_{16}
$$


Refer [[Digital Logic Design Lecture 6#HexaDecimal Numbers|Hexa Decimal Numbers]] for HexaDecimal Definition.

## Binary-Coded Decimal (BCD)

Binary-Coded Decimal (BCD) is a class of binary encodings of decimal numbers where each decimal digit is represented by a fixed number of binary digits, usually four or eight. The most common encoding is the 4-bit encoding, where each digit of a decimal number is represented by its binary equivalent.

### Characteristics of BCD
- **Decimal Digits**: Each of the decimal digits (0-9) is represented by a 4-bit binary number.
- **Representation**: Unlike binary representation where the entire number is converted to binary, in BCD each decimal digit is individually converted to binary.

### Example of BCD Representation

For example, the decimal number 259 in BCD is represented as follows:

1. **Decimal Number**: 259
2. **BCD Representation**:
   - 2 is represented as 0010
   - 5 is represented as 0101
   - 9 is represented as 1001

Thus, $(259_{10}$ is represented in BCD as $(0010 0101 1001_{BCD})$.

### Advantages of BCD
- **Easy Conversion**: Conversion between decimal and BCD is straightforward because each digit is independently converted.
- **Simple Arithmetic Operations**: Simplifies the design of digital systems, particularly in arithmetic operations.

### Disadvantages of BCD
- **Inefficiency**: BCD is less space-efficient compared to pure binary representation because it requires more bits to represent a number.
- **Complex Arithmetic Logic**: Arithmetic operations can be more complex and require additional logic compared to pure binary operations.

### Applications of BCD
- **Digital Clocks**: Time display systems use BCD to represent hours, minutes, and seconds.
- **Calculators**: Most electronic calculators use BCD for internal arithmetic.
- **Digital Meters**: Digital voltmeters and other measuring instruments use BCD for representing the measured values.

### Example Conversions

Here is a table showing decimal digits and their corresponding BCD representations:

| Decimal | BCD    |
|---------|--------|
| 0       | 0000   |
| 1       | 0001   |
| 2       | 0010   |
| 3       | 0011   |
| 4       | 0100   |
| 5       | 0101   |
| 6       | 0110   |
| 7       | 0111   |
| 8       | 1000   |
| 9       | 1001   |

### Conversion Example

Convert the decimal number \(735\) to BCD:

1. **Decimal Number**: 735
2. **BCD Conversion**:
   - 7 is represented as 0111
   - 3 is represented as 0011
   - 5 is represented as 0101

Thus, \(735_{10}\) is represented in BCD as \(0111\ 0011\ 0101_{BCD}\).

### Summary
BCD is a useful encoding method for decimal digits in digital systems where ease of conversion and display is crucial, despite its inefficiency in terms of storage space compared to pure binary representation.


### Gray Code

**Gray Code** is a binary numeral system where two successive values differ in only one bit. It is also known as the **Reflected Binary Code**.

### Characteristics of Gray Code

1. **Single Bit Difference**: 
   - Each number in the sequence differs from the previous one by only one bit.
   - This property reduces errors in digital systems, especially in applications like analog to digital converters (ADCs).

2. **Cyclic Nature**:
   - Gray Code sequences are cyclic. The transition from the highest value back to zero also changes only one bit.
   
### Conversion Between Binary and Gray Code

1. **Binary to Gray Code**:
   - The most significant bit (MSB) of the Gray Code is the same as the MSB of the binary code.
   - Each subsequent bit of the Gray Code is obtained by XORing the current binary bit with the previous binary bit.

   $$ 
   G_n = B_n \oplus B_{n-1} 
   $$
   where $latex G_n$ is the $latex n^{th}$ bit of the Gray Code and $latex B_n$ is the $latex n^{th}$ bit of the binary code.

2. **Gray Code to Binary**:
   - The MSB of the binary code is the same as the MSB of the Gray Code.
   - Each subsequent binary bit is obtained by XORing the previous binary bit with the current Gray Code bit.

   $$ 
   B_n = G_n \oplus B_{n-1} 
   $$

### Example of Binary to Gray Code Conversion

Let's convert the binary number $latex 1011_2$ to Gray Code:

1. **MSB remains the same**:
   $$ 
   G_3 = B_3 = 1 
   $$

2. **Next bit**:
   $$ 
   G_2 = B_3 \oplus B_2 = 1 \oplus 0 = 1 
   $$

3. **Next bit**:
   $$ 
   G_1 = B_2 \oplus B_1 = 0 \oplus 1 = 1 
   $$

4. **Next bit**:
   $$ 
   G_0 = B_1 \oplus B_0 = 1 \oplus 1 = 0 
   $$

So, $latex 1011_2$ in binary converts to $latex 1110_2$ in Gray Code.

### Example of Gray Code to Binary Conversion

Let's convert the Gray Code $latex 1110_2$ back to binary:

1. **MSB remains the same**:
   $$ 
   B_3 = G_3 = 1 
   $$

2. **Next bit**:
   $$ 
   B_2 = G_2 \oplus B_3 = 1 \oplus 1 = 0 
   $$

3. **Next bit**:
   $$ 
   B_1 = G_1 \oplus B_2 = 1 \oplus 0 = 1 
   $$

4. **Next bit**:
   $$ 
   B_0 = G_0 \oplus B_1 = 0 \oplus 1 = 1 
   $$

So, $latex 1110_2$ in Gray Code converts back to $latex 1011_2$ in binary.

### Applications of Gray Code

1. **Error Minimization**:
   - Used in rotary encoders to prevent errors during the transition from one position to another.
   - Minimizes errors in digital systems due to single-bit changes.

2. **Digital Systems**:
   - Used in Karnaugh maps to simplify Boolean expressions.
   - Useful in ADCs and other digital communication systems.

### Summary

- **Gray Code** ensures that only one bit changes at a time, which is useful for reducing errors in digital systems.
- **Conversion** between binary and Gray Code involves simple XOR operations.
- **Applications** of Gray Code include error minimization in rotary encoders and simplification of Boolean expressions in digital systems.


## Binary to Gray

- Step 1 Convert Decimal Number to Binary
- Step 2 we write it down horizontally sequentially
- 
# References


###### Information
- date: 2024.08.06
- time: 13:12