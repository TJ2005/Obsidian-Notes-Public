# Extended Euclidean Theorem

## Introduction
The Extended Euclidean Theorem is an extension of the Euclidean Algorithm, which is used to find the greatest common divisor (GCD) of two integers. It provides a way to express the GCD as a linear combination of the two integers.

---

## Theorem
For any integers $a$ and $b$, there exist integers $x$ and $y$ such that:
$$\text{gcd}(a, b) = ax + by$$

The integers $x$ and $y$ can be determined using the Extended Euclidean Algorithm.

---

## Steps for the Extended Euclidean Algorithm

1. **Apply the Euclidean Algorithm**:
   Use repeated division to find $\text{gcd}(a, b)$ by:
   $$a = bq + r$$
   $$b = rq' + r'$$
   Continue until the remainder $r = 0$. The GCD is the last non-zero remainder.

2. **Work Backwards**:
   Substitute the remainders from the Euclidean steps to express the GCD as a linear combination of $a$ and $b$.

---

## Example

Find $\text{gcd}(56, 15)$ and express it as $56x + 15y = \text{gcd}(56, 15)$.

1. **Step 1: Euclidean Algorithm**:
   $$56 = 15 \cdot 3 + 11$$
   $$15 = 11 \cdot 1 + 4$$
   $$11 = 4 \cdot 2 + 3$$
   $$4 = 3 \cdot 1 + 1$$
   $$3 = 1 \cdot 3 + 0$$

   So, $\text{gcd}(56, 15) = 1$.

2. **Step 2: Work Backwards**:
   Start with the last non-zero remainder:
   $$1 = 4 - 3 \cdot 1$$
   Substitute $3 = 11 - 4 \cdot 2$:
   $$1 = 4 - (11 - 4 \cdot 2) \cdot 1$$
   $$1 = 4 - 11 + 4 \cdot 2$$
   $$1 = 3 \cdot 4 - 11$$
   Substitute $4 = 15 - 11 \cdot 1$:
   $$1 = 3 \cdot (15 - 11 \cdot 1) - 11$$
   $$1 = 3 \cdot 15 - 3 \cdot 11 - 11$$
   $$1 = 3 \cdot 15 - 4 \cdot 11$$
   Substitute $11 = 56 - 15 \cdot 3$:
   $$1 = 3 \cdot 15 - 4 \cdot (56 - 15 \cdot 3)$$
   $$1 = 3 \cdot 15 - 4 \cdot 56 + 4 \cdot 15 \cdot 3$$
   $$1 = 15 \cdot (3 + 12) - 4 \cdot 56$$
   $$1 = 15 \cdot 39 - 4 \cdot 56$$

   So, $x = -4$ and $y = 39$:
   $$1 = -4 \cdot 56 + 39 \cdot 15$$

---

## Applications

1. **Finding Modular Inverses**:
   If $a$ and $m$ are coprime, the Extended Euclidean Algorithm can compute $a^{-1} \mod m$.

2. **Solving Linear Diophantine Equations**:
   The algorithm helps find integer solutions for equations of the form $ax + by = c$.

3. **Cryptography**:
   Used in algorithms like RSA for key generation and modular arithmetic operations.
