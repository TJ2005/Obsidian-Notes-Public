---
Title: Digital Logic Design Lecture 3
Status: 
marker: 
tags: 
Date: 2024-07-23
Time: 2024-07-23T13:00:00
---
# Digital Logic Design Lecture 3

# Index
1. [Looking back to conversion methods](#looking-back-to-conversion-methods)
2. [8 Bit Signed Number & Signed Magnitude Representation](#8-bit-signed-number--signed-magnitude-representation)
   - [Positive](#positive)
   - [Negative](#negative)
3. [Ones Complement Representation](#ones-complement-representation)
4. [Two's Complement Basics](#twos-complement-basics)
   - [Example: Representing +7 and -7](#example-representing-7-and-7)
   - [Correct Representation of `1000`](#correct-representation-of-1000)
   - [Range of 4-bit Two's Complement](#range-of-4-bit-twos-complement)
5. [Summary of Two's Bit Complement](#summary-of-twos-bit-complement)

# Content

## Looking back to conversion methods
Refer [[Digital Logic Design Lecture 2|DLD Lecture 2]]

## 8 Bit signed Number & Signed Magnitude Representation
To represent a positive number or a negative number we use a bit.
##### Positive 
For Positive we use bit zero ( 0 ) in the MSB Position to represent a positive binary number.
##### Negative
For Negative we use a bit ( 1 ) in the MSB Position to represent a negative binary number.

## Ones Complement Representation
We can have this only for binary numbers only.
In this complement representation the bits are flipped for lets say a not gate.
for example `1011000110` would be `0100111001`

In a two's complement system, the binary number `1000` does not represent -7. It represents -8. Let's clarify this with more detail.

### Two's Complement Basics

1. **Positive Numbers**:
   - Positive numbers are represented in their straightforward binary form.

2. **Negative Numbers**:
   - Negative numbers are represented by taking the two's complement of their absolute value.

### Example: Representing +7 and -7

1. **+7 in 4-bit Binary**:
   - `0111`

2. **-7 in 4-bit Two's Complement**:
   - Start with the binary of +7: `0111`
   - Invert all bits: `1000`
   - Add 1: `1000` + `1` = `1001`
   - So, `-7` is represented as `1001`.

### Correct Representation of `1000`

- `1000` in a 4-bit two's complement system represents -8, not -7.

### Range of 4-bit Two's Complement

In a 4-bit two's complement system, the values range from -8 to +7:

- `0000` = 0
- `0001` = 1
- `0010` = 2
- `0011` = 3
- `0100` = 4
- `0101` = 5
- `0110` = 6
- `0111` = 7
- `1000` = -8
- `1001` = -7
- `1010` = -6
- `1011` = -5
- `1100` = -4
- `1101` = -3
- `1110` = -2
- `1111` = -1

### Summary of Two's Bit Complement

- **+7**: `0111`
- **-7**: `1001`
- **+8** is not representable in a 4-bit two's complement system, as the range is from -8 to +7.

For an 8-bit two's complement system, the range is from -128 to +127:

- **+127**: `0111 1111`
- **-128**: `1000 0000`

This system ensures that each binary number has a unique interpretation, avoiding any confusion.

# References
