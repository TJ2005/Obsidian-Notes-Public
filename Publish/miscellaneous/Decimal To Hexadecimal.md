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