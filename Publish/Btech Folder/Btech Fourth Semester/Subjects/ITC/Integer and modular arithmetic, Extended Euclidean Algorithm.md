---
Title: Integer and modular arithmetic, Extended Euclidean Algorithm
Status: 
marker:
  - "[[ITC Unit 3]]"
  - "[[Introduction To Cryptography (ITC)]]"
tags:
  - BTech
  - Note
Date: 2025.04.22
Time: 10:18
---
# Euclidean Algorithm and Modular Arithmetic: A Comprehensive Guide

> [!Related Notes]
> 
> - [[Integer and modular arithmetic, Extended Euclidean Algorithm]]
> - [[Linear Congruence, Algebraic structures (Group, Rings, and Fields) ,Galois Field]]
> - [[Modern Block Cipher and its components(D- Boxes and S-Boxes)]]
> - [[Product ciphers, stream ciphers (FSR and LFSR)]]
> - [[Attacks on stream and block ciphers]]
> - [[DES]]
> - [[AES, modes of operations

The Euclidean Algorithm and modular arithmetic are fundamental concepts in number theory with wide-ranging applications in cryptography, computer science, and mathematics. This note provides a clear explanation of these concepts with detailed examples.

## The Euclidean Algorithm

The Euclidean Algorithm is an efficient method for computing the greatest common divisor (GCD) of two integers. It works by repeatedly applying the division algorithm until we reach a remainder of zero.

### Basic Procedure

1. Start with two positive integers a and b (where a ≥ b)
2. Divide a by b to get a quotient q and remainder r: a = b·q + r
3. If r = 0, then $GCD(a,b)$ = b and we're done
4. Otherwise, replace a with b and b with r, then repeat from step 2

The algorithm can be represented in a tabular format with columns for:
- Q: Quotient
- A: First number (dividend)
- B: Second number (divisor)
- R: Remainder

### Example: GCD(1071, 462)

| Q | A    | B   | R   |
|---|------|-----|-----|
| 2 | 1071 | 462 | 147 |
| 3 | 462  | 147 | 21  |
| 7 | 147  | 21  | 0   |
| - | 21   | 0   | -   |

Since the remainder is 0, the GCD is the last non-zero remainder: 21.

### Why It Works

The key insight is that if a = b·q + r, then any common divisor of a and b must also divide r. Conversely, any common divisor of b and r must also divide a. Therefore:

$$ \text{GCD}(a, b) = \text{GCD}(b, r) $$

This property allows us to reduce the problem to smaller numbers until we reach a point where one number divides the other exactly, giving us the GCD.

## Extended Euclidean Algorithm

The Extended Euclidean Algorithm not only finds the GCD of two integers but also expresses it as a linear combination of the original numbers.

### Purpose

For integers a and b, the Extended Euclidean Algorithm finds integers s and t such that:

$$ \text{GCD}(a, b) = s \cdot a + t \cdot b $$

This is particularly useful for finding modular multiplicative inverses.

### Procedure

The Extended Euclidean Algorithm adds two additional columns to track the coefficients:

1. Start with a and b, and initialize:
   - T₁ = 0, T₂ = 1 for the first row
   - T₁ = 1, T₂ = 0 for the second row (if needed)
2. For each step, calculate T = T₁ - T₂·Q
3. Continue until B becomes 0
4. The value of T₁ in the final row gives the coefficient for the smaller original number

### Example: Finding the Multiplicative Inverse of 3 mod 5

| Q | A | B | R | T₁ | T₂ | T  |
|---|---|---|---|----|----|----|
| 1 | 5 | 3 | 2 | 0  | 1  | -1 |
| 1 | 3 | 2 | 1 | 1  | -1 | 2  |
| 2 | 2 | 1 | 0 | -1 | 2  | -5 |
| - | 1 | 0 | - | 2  | -5 | -  |

The multiplicative inverse of 3 mod 5 is 2, since 3·2 ≡ 1 (mod 5).

### How to Read the Table

- **Q**: The quotient when A is divided by B
- **A**: The dividend (starts with the larger number)
- **B**: The divisor (starts with the smaller number)
- **R**: The remainder when A is divided by B
- **T₁**: The coefficient from the previous row's T₂
- **T₂**: The coefficient from the previous row's T
- **T**: Calculated as T₁ - T₂·Q

The algorithm terminates when B becomes 0, and the GCD is the last non-zero value in column B.

## Modular Arithmetic

Modular arithmetic is a system where numbers "wrap around" after reaching a certain value called the modulus.

### Basic Concept

In modular arithmetic, we focus on the remainder when dividing by a fixed number (the modulus). When we write:

$$ a \equiv b \pmod{n} $$

We mean that a and b have the same remainder when divided by n, or equivalently, n divides (a-b).

### Quotient-Remainder Theorem

For any integers a and n (where n > 0), there exist unique integers q and r such that:

$$ a = q \cdot n + r $$

where 0 ≤ r < n. Here:
- a is the dividend
- n is the divisor
- q is the quotient
- r is the remainder

In modular arithmetic, we write r = a mod n.

### Residue Classes

A residue class (or equivalence class) modulo n is the set of all integers that have the same remainder when divided by n.

For an integer a and modulus m, the residue class of a modulo m is:

$$ 
[a]_m = \{a + km \mid k \in \mathbb{Z}\} $$

This represents all integers that are congruent to a modulo m.

### Example: Residue Class of 2 mod 5

The residue class of 2 modulo 5 consists of all numbers in the form 2 + 5k, where k is any integer:

- For k = -2: 2 + 5(-2) = 2 - 10 = -8
- For k = -1: 2 + 5(-1) = 2 - 5 = -3
- For k = 0: 2 + 5(0) = 2
- For k = 1: 2 + 5(1) = 2 + 5 = 7
- For k = 2: 2 + 5(2) = 2 + 10 = 12
- For k = 3: 2 + 5(3) = 2 + 15 = 17

So the residue class[2]₅ = {..., -8, -3, 2, 7, 12, 17, ...}

## Modular Operations

Modular arithmetic supports operations similar to regular arithmetic:

1. **Addition**: (a + b) mod n = ((a mod n) + (b mod n)) mod n
2. **Subtraction**: (a - b) mod n = ((a mod n) - (b mod n)) mod n
3. **Multiplication**: (a × b) mod n = ((a mod n) × (b mod n)) mod n
4. **Division**: Requires finding the modular multiplicative inverse

### Modular Multiplicative Inverse

For an integer a and modulus m, the modular multiplicative inverse of a is an integer a⁻¹ such that:

$$ a \cdot a^{-1} \equiv 1 \pmod{m} $$

The inverse exists if and only if a and m are coprime (gcd(a,m) = 1). We use the Extended Euclidean Algorithm to find it.

## Applications

These concepts have numerous applications:
- Cryptography (RSA, Diffie-Hellman)
- Hash functions
- Random number generation
- Error detection and correction
- Clock arithmetic
- Calendar calculations

By understanding these fundamental concepts, you'll have powerful tools for solving problems in number theory and computer science.

Citations:
[1] https://www.khanacademy.org/computing/computer-science/cryptography/modarithmetic/a/the-euclidean-algorithm
[2] https://www.geeksforgeeks.org/extended-euclid-division-algorithm/
[3] https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm
[4] https://en.wikipedia.org/wiki/Modular_arithmetic
[5] https://en.wikipedia.org/wiki/Euclidean_algorithm
[6] https://www.geeksforgeeks.org/modular-arithmetic/
[7] http://www.math.ualberta.ca/~isaac/math324/s12/euclidean.pdf
[8] https://www.geeksforgeeks.org/euclidean-algorithms-basic-and-extended/
[9] https://extendedeuclideanalgorithm.com/xea.php
[10] https://sites.math.rutgers.edu/~greenfie/gs2004/euclid.html
[11] https://www.shiksha.com/online-courses/articles/euclidean-algorithm/
[12] https://www.wscubetech.com/resources/dsa/euclidean-algorithm
[13] https://extendedeuclideanalgorithm.com/code.php
[14] https://www.w3schools.com/dsa/dsa_ref_euclidean_algorithm.php
[15] https://www.youtube.com/watch?v=hB34-GSDT3k
[16] https://cp-algorithms.com/algebra/extended-euclid-algorithm.html
[17] https://math.libretexts.org/Bookshelves/Combinatorics_and_Discrete_Mathematics/Elementary_Number_Theory_(Barrus_and_Clark)/01:_Chapters/1.08:_The_Euclidean_Algorithm
[18] https://brilliant.org/wiki/extended-euclidean-algorithm/
[19] https://www.whitman.edu/mathematics/higher_math_online/section03.03.html
[20] https://www.khanacademy.org/computing/computer-science/cryptography/modarithmetic/a/what-is-modular-arithmetic
[21] https://solitaryroad.com/c304.html
[22] https://artofproblemsolving.com/wiki/index.php/Modular_arithmetic/Introduction
[23] https://dummit.cos.northeastern.edu/teaching_fa23_1365/1365_lecture_16_residue_classes_and_modular_arithmetic.pdf
[24] https://courses.smp.uq.edu.au/MATH2301/Chapter2.pdf
[25] https://dummit.cos.northeastern.edu/docs/numthy_2_modular_arithmetic.pdf
[26] https://www.youtube.com/watch?v=Q_V_itu_kbs
[27] https://en.wikipedia.org/wiki/Modulo
[28] https://artofproblemsolving.com/wiki/index.php/Residue_class
[29] https://www.youtube.com/watch?v=c7gWmEd7EmU
[30] https://study.com/learn/lesson/modular-arithmetic-rules-properties-what-is-modular-arithmetic.html
[31] https://runestone.academy/ns/books/published/thinkcspy/SimplePythonData/OperatorsandOperands.html
[32] https://www.math.cmu.edu/~bkell/21110-2010s/extended-euclidean.html
[33] https://cp-algorithms.com/algebra/euclid-algorithm.html
[34] https://forthright48.com/extended-euclidean-algorithm/
[35] https://brilliant.org/wiki/modular-arithmetic/
[36] https://calcworkshop.com/number-theory/modular-arithmetic/
[37] https://www.geeksforgeeks.org/modulus-operator-in-programming/
[38] https://en.wikipedia.org/wiki/Residue_number_system
[39] https://math.stackexchange.com/questions/229906/every-residue-class-pmod2a-can-be-written-as-pm-5r-for-some-r
[40] https://blog.mattclemente.com/2019/07/12/modulus-operator-modulo-operation/

---
Answer from Perplexity: pplx.ai/share
# References


###### Information
- date: 2025.04.22
- time: 10:18