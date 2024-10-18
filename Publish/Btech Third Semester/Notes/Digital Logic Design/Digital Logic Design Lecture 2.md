---
Title: Digital Logic Design Lecture 2
Status: 
marker:
  - "[[btech]]"
tags:
  - BTech
Date: 2024-07-18
Time: 08:43
---
## Digital Logic Design Lecture 2

### Index

* [Conversion](#conversion)
    * [Binary to Decimal](#binary-to-decimal)
        * [Integer](#integer)
        * [Fractional](#fractional)
    * [Decimal to Binary](#decimal-to-binary)
        * [Integer](#integer-1)
        * [Fractional](#fractional-1)
* [Why Binary?](#why-binary)
* [Conversion Methods](#conversion-methods)

### Why Binary?
Computers use binary because it simplifies the hardware. Electrical circuits can easily represent two states: on (1) and off (0). These states correspond to binary digits. Additionally, binary arithmetic is simpler than decimal arithmetic, making computations more efficient.

### Conversion Methods

#### Binary to Decimal
* **Integer:**
  * Each binary digit (bit) represents a power of 2.
  * Multiply each bit by its corresponding power of 2.
  * Add the results.
  
  *Example:* 1011 = 1\*2^3 + 0\*2^2 + 1\*2^1 + 1\*2^0 = 8 + 0 + 2 + 1 = 11

* **Fractional:**
  * Each binary digit after the decimal point represents a negative power of 2.
  * Multiply each bit by its corresponding negative power of 2.
  * Add the results.

  *Example:* 0.110 = 1\*2^-1 + 1\*2^-2 + 0\*2^-3 = 0.5 + 0.25 + 0 = 0.75

#### Decimal to Binary
* **Integer:**
  * Continuously divide the decimal number by 2.
  * The remainders form the binary equivalent from right to left.
  
  *Example:* Convert 13 to binary:
  * 13 / 2 = 6, remainder 1
  * 6 / 2 = 3, remainder 0
  * 3 / 2 = 1, remainder 1
  * 1 / 2 = 0, remainder 1
  * Binary equivalent: 1101

* **Fractional:**
  * Continuously multiply the fractional part by 2.
  * The integer part of the result becomes the next binary digit.
  * Repeat until the fractional part becomes 0 or the desired precision is reached.
  
  *Example:* Convert 0.625 to binary:
  * 0.625 \* 2 = 1.25 -> Integer part: 1
  * 0.25 \* 2 = 0.5 -> Integer part: 0
  * 0.5 \* 2 = 1.0 -> Integer part: 1
  * Binary equivalent: 0.101