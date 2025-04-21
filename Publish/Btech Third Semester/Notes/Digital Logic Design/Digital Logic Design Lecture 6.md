---
Title: Digital Logic Design Lecture 6
Status: 
marker:
  - "[[btech]]"
  - "[[Binary Numbers]]"
  - "[[Octal Numbers]]"
  - "[[Hexa Decimal Numbers]]"
tags:
  - BTech
Date: 2024.08.01
Time: 08:19
---
# Digital Logic Design Lecture 6

# Main note

## Octal Numbers

#### Properties
- It has base 8
- 0,1,2,3,4,5,6,7
- 2^3 = 8 Thus we require 3 bits of binary combinations to represent an octal number

## Conversion

#### Octal to Decimal
- We multiply \(8^{n-1}\) to each of the digits with respect to their positions.

###### Example
Converting 6327.4051
$$ = 6 \times 8^3 + 3 \times 8^2 + 2 \times 8^1 + 7 \times 8^0 + 4 \times 8^{-1} + 0 \times 8^{-2} + 5 \times 8^{-3} + 1 \times 8^{-4} $$

Now, calculate each term:
$$ = 6 \times 512 + 3 \times 64 + 2 \times 8 + 7 \times 1 + 4 \times \frac{1}{8} + 0 \times \frac{1}{64} + 5 \times \frac{1}{512} + 1 \times \frac{1}{4096} $$

Simplify:
$$ = 3072 + 192 + 16 + 7 + 0.5 + 0 + 0.009765625 + 0.000244140625 $$

Adding all terms together:
$$ = 3287.509009765625 $$

Thus, the decimal equivalent of the octal number 6327.4051 is:
$$ = 3287.509009765625 $$
#### Decimal To Octal
We keep dividing by 8 and storing the remainder in the answer vector, and then take the remnant of the quotient and divide it by 8 until it's 0.

##### Example
Convert \( 247_{10} \) to octal

1. Divide 247 by 8:
$$ 247 \div 8 = 30 \text{ remainder } 7 $$

2. Divide 30 by 8:
$$ 30 \div 8 = 3 \text{ remainder } 6 $$

3. Divide 3 by 8:
$$ 3 \div 8 = 0 \text{ remainder } 3 $$

Now, reading the remainders from bottom to top, we get:
$$ 247_{10} = 367_{8} $$
##### Important Note

When Float Values are present instead of dividing with 8 we multiply.](<#### Decimal To Octal (Float Values)
When float values are present, instead of dividing by 8, we multiply by 8 and take the integer part as the next digit in the octal representation.

##### Example
Convert \( 0.6875_{10} \) to octal

1. Multiply 0.6875 by 8:
$$ 0.6875 \times 8 = 5.5 $$
Take the integer part 5.

2. Multiply the fractional part 0.5 by 8:
$$ 0.5 \times 8 = 4.0 $$
Take the integer part 4.

Since the fractional part is now 0, we stop here.

Reading the integer parts from top to bottom, we get:
$$ 0.6875_{10} = 0.54_{8} $$
#### Octal To Binary
Three binary bits are required for each octal digit, based on the logic that $(2^3 = 8)$.

##### Example
Convert $(736)_8$
$(736)_{8}~=~(111 ~011~ 110)$
We simply replaced each digit with their binary counterparts

#### Binary To Octal
Three binary bits correspond to each octal digit, based on the logic that \(2^3 = 8\).

##### Example
Convert \( (111011110)_2 \) to octal

1. Group the binary digits into sets of three, starting from the right:
$$ 111 \ 011 \ 110 $$

2. Convert each group of three binary digits to their octal equivalent:
- \(111\) in binary is \(7\) in octal.
- \(011\) in binary is \(3\) in octal.
- \(110\) in binary is \(6\) in octal.

Therefore:
$$ (111011110)_2 = (736)_8 $$


#### Fractional Binary to Octal 
For fractional Part group three bits and equivalent decimal number to get octal number from left to right side w.r.t Decimal Point.
###### Example
$(0.10100110)_2~=~(0.101~001~100)_2$
$~~~~~~~~~~~~~~~~~~~~~~~~~=(0.514)_8$

## HexaDecimal Numbers

### Conversion
#### Hexadecimal Number to Decimal
We multiply each digit with \(16^{n-1}\) and add them all.

###### Example
Convert \((3A.2F)_{16}\) to decimal

1. Separate the number into its integer and fractional parts:
$$ 3A.2F_{16} $$

2. Convert each digit to its decimal equivalent:
- \(3\) in hexadecimal is \(3\) in decimal.
- \(A\) in hexadecimal is \(10\) in decimal.
- \(2\) in hexadecimal is \(2\) in decimal.
- \(F\) in hexadecimal is \(15\) in decimal.

3. Multiply each digit by \(16^{n-1}\) where \(n\) is the position from the decimal point:
$$ = 3 \times 16^1 + 10 \times 16^0 + 2 \times 16^{-1} + 15 \times 16^{-2} $$

4. Calculate each term:
$$ = 3 \times 16 + 10 \times 1 + 2 \times \frac{1}{16} + 15 \times \frac{1}{256} $$
$$ = 48 + 10 + \frac{2}{16} + \frac{15}{256} $$
$$ = 48 + 10 + 0.125 + 0.05859375 $$

5. Add all terms together:
$$ = 58.18359375 $$

Therefore:
$$ (3A.2F)_{16} = 58.18359375_{10} $$
### Decimal To Hexadecimal
To convert a decimal number to hexadecimal, we repeatedly divide the number by 16 and store the remainder. For the fractional part, we multiply by 16 and take the integer part. We continue this process until the quotient is 0 (for the integer part) and the fractional part reaches the desired precision.

#### Example
Convert \( 58.18359375_{10} \) to hexadecimal

1. Convert the integer part (58):

- Divide 58 by 16:
$$ 58 \div 16 = 3 \text{ remainder } 10 $$
- The remainder 10 corresponds to 'A' in hexadecimal.

- Divide 3 by 16:
$$ 3 \div 16 = 0 \text{ remainder } 3 $$

So, the integer part \( 58_{10} = 3A_{16} \).

2. Convert the fractional part (0.18359375):

- Multiply 0.18359375 by 16:
$$ 0.18359375 \times 16 = 2.9375 $$
Take the integer part 2.

- Multiply the remaining fractional part 0.9375 by 16:
$$ 0.9375 \times 16 = 15.0 $$
Take the integer part 15, which corresponds to 'F' in hexadecimal.

So, the fractional part \( 0.18359375_{10} = 0.2F_{16} \).

Combining both parts:
$$ 58.18359375_{10} = 3A.2F_{16} $$

## HexaDecimal to Binary

## Example 2.30
### Conversion of Hexadecimal to Binary

**Problem:**
Convert \((2F9A)_{16}\) to an equivalent binary number.

**Solution:**
Using Table 2.7, find the binary equivalent of each hexadecimal digit.

$$
(2F9A)_{16} = (0010 1111 1001 1010)_{2}
$$

$$
(2F9A)_{16} = (0010111110011010)_{2}
$$

### Steps:

1. **Hex Digit: 2**
   - Binary Equivalent: `0010`

2. **Hex Digit: F**
   - Binary Equivalent: `1111`

3. **Hex Digit: 9**
   - Binary Equivalent: `1001`

4. **Hex Digit: A**
   - Binary Equivalent: `1010`

Thus, combining these binary equivalents, we get:

$$
2F9A_{16} = 0010 \ 1111 \ 1001 \ 1010_{2}
$$

Or, without spaces:

$$
2F9A_{16} = 0010111110011010_{2}
$$




## Hexadecimal to Binary Conversion

Hexadecimal numbers can be converted into equivalent binary numbers by replacing each hex digit by its equivalent 4-bit binary number.

### Example 2.30
**Problem:**
Convert $((2F9A)_{16})$ to an equivalent binary number.

**Solution:**
Using Table 2.7, find the binary equivalent of each hexadecimal digit.

$$
(2F9A)_{16} = (0010 1111 1001 1010)_{2}
$$

$$
(2F9A)_{16} = (0010111110011010)_{2}
$$

### Steps:

1. **Hex Digit: 2**
   - Binary Equivalent: `0010`

2. **Hex Digit: F**
   - Binary Equivalent: `1111`

3. **Hex Digit: 9**
   - Binary Equivalent: `1001`

4. **Hex Digit: A**
   - Binary Equivalent: `1010`

Thus, combining these binary equivalents, we get:



# References


###### Information
- date: 2024.08.01
- time: 08:19