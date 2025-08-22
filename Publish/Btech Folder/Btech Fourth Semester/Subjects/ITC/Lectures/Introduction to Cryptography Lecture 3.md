---
Title: Introduction to Cryptography Lecture 3
Status: 
marker: 
tags: 
Date: 2025.01.11
Time: 11:19
---
# Introduction to Cryptography Lecture 3

## Affine Cipher

### Encrypting with Affine Cipher
- Monoalphabetic substitution cipher
- Example encryption:
    $$E(x)=(ax+b)\mod m$$
    - $m$ is the size of the alphabet array.
        - For simplicity, we use alphabets where $m = 26$.
    - $a$ and $b$ are keys of the cipher.
    - $a$ must be chosen such that $a$ and $m$ are coprime.
- Decryption involves a different inverse logic.

---

### Decrypting with Affine Cipher

- Decryption formula:
    $$D(y)=a^{-1}(y-b)\mod m$$
    Where:
    - $y$ is the encrypted character.
    - $a^{-1}$ is the modular multiplicative inverse of $a$ modulo $m$.
        $$a^{-1} \text{ satisfies: } (a\cdot a^{-1})\mod m = 1$$
    - $b$ is the key used for shifting.
    - $m$ is the size of the alphabet (e.g., $m=26$ for the English alphabet).

---

### Steps for Decryption

1. **Find Modular Inverse**:
   Ensure $a$ and $m$ are coprime, then calculate $a^{-1}$ using the Extended Euclidean Algorithm.
2. **Apply the Formula**:
   Subtract $b$ from the encrypted value $y$, multiply by $a^{-1}$, and reduce modulo $m$.

---

### Example

Assume $m=26$, $a=5$, and $b=8$:
Encrypted character $y$: 15 (corresponds to 'P').

1. **Find $a^{-1}$**:
   $$a^{-1}=21, \text{ as } (5\cdot 21)\mod 26 = 1$$

2. **Decrypt using the formula**:
   $$D(15)=21\cdot(15-8)\mod 26$$
   $$D(15)=21\cdot 7\mod 26$$
   $$D(15)=147\mod 26=17$$

So, the decrypted character corresponds to 17 (which is 'R').

---

# Questions

## Question 1
Suppose $K = (9, 22)$ is a key in a cipher over mod 26. It should follow the form: $$d_k(y) = r y + s$$ where $r, s \in \mathbb{Z}$ (integers).
## Answer 1

### Step 1: Understand the form
We are given:
- $K = (9, 22)$, where:
  - $a = 9$ (multiplicative key),
  - $b = 22$ (additive key),
  - $m = 26$ (modulus for the alphabet size).

The decryption formula is:
$$d_k(y) = a^{-1}(y - b)$$

Here:
- $a^{-1}$ is the modular inverse of $a$ modulo $m$.
- $(y - b)$ shifts the encrypted character back using $b$.

---

### Step 2: Find $a^{-1}$ (modular inverse of $a$)
We need $a^{-1}$ such that:
$$(a \cdot a^{-1}) \mod m = 1$$

Using the **Extended Euclidean Algorithm**, find $9^{-1}$ modulo 26:
- $9^{-1} = 3$ (as $9 \cdot 3 \mod 26 = 1$).

---

### Step 3: Substitute values into the formula
Replace $a^{-1} = 3$ and $b = 22$ into the formula:
$$d_k(y) = 3(y - 22)$$

---

### Step 4: Simplify the formula
Expand and simplify:
1. Distribute $3$:
   $$d_k(y) = 3y - 3 \cdot 22$$
2. Calculate $3 \cdot 22 \mod 26$:
   $$3 \cdot 22 = 66, \text{ and } 66 \mod 26 = 14.$$
3. Substitute back:
   $$d_k(y) = 3y - 14$$

To match the form $d_k(y) = r y + s$:
- $r = 3$,
- $s = -14 \mod 26 = 12$.

---

### Final Answer:
The decryption formula is:
$$d_k(y) = 3y + 12$$
where:
- $r = 3$,
- $s = 12$.

## Question 2
$e(x)=3x+10~mod~26$ is used to encrypt a plaintext. Find the decryption function $d(y)=cy+d~mod~26$. If the Affine Cipher yields the following cipher text find the corresponding plaintext NAXT.

## Answer 2
Here, 3 and 10 are $a$ and $b$.
