---
Title: Digital Logic Design Lecture 4
Status: 
marker: 
tags: 
Date: 2024.07.25
Time: "{time:HH:mm}}"
---
# Digital Logic Design Lecture 4

# Index
# Main note


##
### Binary Addition
Since there are only two digits in binary we involve only two digits.

| Augend | Addend | Sum | Carry | Result |
|--------|--------|-----|-------|--------|
|   0    |   0    |  0  |   0   |    0   |
|   0    |   1    |  1  |   0   |    1   |
|   1    |   0    |  1  |   0   |    1   |
|   1    |   1    |  0  |   1   |   10   |
![[Pasted image 20240725084638.png]]
### Binary Subtraction
Here is a similar table for binary subtraction:

| Minuend | Subtrahend | Difference | Borrow | Result |
|---------|------------|------------|--------|--------|
|    0    |     0      |     0      |   0    |   0    |
|    0    |     1      |     1      |   1    |  -1    |
|    1    |     0      |     1      |   0    |   1    |
|    1    |     1      |     0      |   0    |   0    |
In binary subtraction:
- The Difference column represents the result of the binary subtraction of the Subtrahend from the Minuend.
- The Borrow column indicates whether a borrow is needed from the next higher bit.
- The Result column shows the final result, taking into account the borrow if necessary.

### Binary Multiplication

Binary multiplication follows the same basic rules as decimal multiplication but is simpler because each digit is either 0 or 1.

| Multiplier | Multiplicand | Product | Result |
|------------|--------------|---------|--------|
|     0      |      0       |    0    |    0   |
|     0      |      1       |    0    |    0   |
|     1      |      0       |    0    |    0   |
|     1      |      1       |    1    |    1   

Note: 
- If either the Multiplier or the Multiplicand is 0, the Product is 0.
- If both the Multiplier and the Multiplicand are 1, the Product is 1.

### Binary Division

Binary division is similar to long division in the decimal system. It involves determining how many times the divisor can be subtracted from the dividend, shifting the quotient, and bringing down bits of the dividend.

| Dividend | Divisor | Quotient | Remainder | Result |
|----------|---------|----------|-----------|--------|
|     0    |    1    |     0    |     0     |   0/1  |
|     1    |    1    |     1    |     0     |   1/1  |
|    10    |    1    |    10    |     0     |  10/1  |
|    10    |   10    |     1    |     0     |  10/10 |

Note: 
- The `Result` column represents the division operation in binary format.
- The `Quotient` is the result of the division.
- The `Remainder` is what is left after the division. If the Divisor perfectly divides the Dividend, the Remainder is 0.

## Two's Complement Arithmetic operations
Certainly! Here is an explanation and tables for addition, subtraction, division, and multiplication using two's complement representation, including how to handle overflow and discarding extra bits.

### Two's Complement Overview
Two's complement is a method for representing signed integers in binary form. The most significant bit (MSB) is the sign bit:
- `0` for positive numbers
- `1` for negative numbers

To find the two's complement of a number:
1. Invert all the bits.
2. Add 1 to the least significant bit (LSB).

### Addition
When adding two binary numbers in two's complement, simply add them bit by bit, just as in regular binary addition, and discard any overflow beyond the fixed number of bits.

```markdown
| Operand A | Operand B | Sum  | Overflow | Result |
|-----------|-----------|------|----------|--------|
|    0101   |    0011   | 1000 |    0     |  1000  |
|    1101   |    0011   | 0000 |    1     |  0000  |
```
Note: Discard any overflow beyond the fixed number of bits.

### Subtraction
Subtraction is performed by adding the two's complement of the subtrahend to the minuend.

```markdown
| Minuend | Subtrahend | Two's Complement of Subtrahend | Sum  | Overflow | Result |
|---------|------------|-------------------------------|------|----------|--------|
|  0101   |    0011    |              1101             | 10010|    1     |  0010  |
|  1101   |    0011    |              1101             | 10110|    1     |  0110  |
```
Note: Discard the overflow bit and consider only the fixed number of bits.

### Multiplication
Multiplication of two's complement numbers follows the same rules as unsigned binary multiplication but with attention to the sign of the result.

```markdown
| Multiplier | Multiplicand | Product | Result |
|------------|--------------|---------|--------|
|    0101    |     0011     | 11111   |  1111  |
|    1101    |     0011     | 11011   |  1011  |
```
Note: Ensure the sign bit is correctly handled and discard overflow bits if necessary.

### Division
Division of two's complement numbers involves the same process as unsigned binary division, but the quotient will have the correct sign based on the operands' signs.

```markdown
| Dividend | Divisor | Quotient | Remainder | Result |
|----------|---------|----------|-----------|--------|
|   0101   |   0011  |    0001  |    0010   |  0101/0011  |
|   1101   |   0011  |    1110  |    1111   |  1101/0011  |
```
Note: Pay attention to the sign of the quotient and remainder, and discard overflow bits.

### Overflow and Discarding Bits
In binary arithmetic using two's complement, any bits beyond the fixed number of bits are discarded. This process ensures that the result fits within the designated bit width (e.g., 8-bit, 16-bit).

For example, if using 4-bit numbers:
- Adding `1101` and `0011` results in `1 0000`. The leading `1` (overflow) is discarded, leaving `0000`.
- Subtracting `0011` from `0101` using two's complement involves adding `0101` and `1101`, resulting in `1 0000`. Again, discard the overflow.

By carefully managing the bits and discarding overflow, we maintain accurate results within the constraints of two's complement arithmetic.
# References


###### Information
- date:: 2024.07.25
- time:: 08:32