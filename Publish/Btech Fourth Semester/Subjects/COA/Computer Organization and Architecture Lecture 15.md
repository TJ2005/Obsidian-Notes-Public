---
Title: "Computer Organization & Architecture Lecture 16"
Status: 
marker: 
tags: 
Date: "2025.03.06"
Time: "16:11"
---
From [[Computer Organization and Architecture Lecture 14]]

---

# **IEEE 754 Floating-Point Representation**

### **Introduction**

IEEE 754 is the standard for representing floating-point numbers in computers. It ensures consistency across different computing systems and architectures. The standard defines multiple formats, including **single precision (32-bit), double precision (64-bit), and extended precision formats**.

### **Structure of IEEE 754 Floating-Point Number**

A floating-point number in IEEE 754 format consists of three main components:

1. **Sign Bit (S)**:
    
    - 1 bit that determines the sign of the number.
    - 00 for positive, 11 for negative.
2. **Exponent (E)**:
    
    - Stored with a bias (e.g., **127** for single precision, **1023** for double precision).
    - Determines the scaling factor.
3. **Mantissa (M) (Fraction)**:
    
    - Stores the significant digits of the number.
    - The actual significand is **1.M** (implicit leading 1 for normalized numbers).

### **Mathematical Representation**

A floating-point number in IEEE 754 format is represented as:

$$±M× B^E$$

Where:

- MM is the **mantissa** (also called the significand).
- BB is the **base**, which is **2** in binary representation.
- EE is the **exponent**, calculated as:

$E=\text{Stored Exponent}−\text{BiasE} = \text{Stored Exponent} - \text{Bias}$

For **single precision (32-bit)**:

$$E=Exponent−127E = \text{Exponent} - 127$$

For **double precision (64-bit)**:

$$E=Exponent−1023E = \text{Exponent} - 1023$$

---

# Questions
Convert -> $1259.125_{10}$ into single & double pre format
### Solve
 - $(1259)_{10}\to(10011101011)_2$
 - $(0.125)_{10}\to(001)_{2}$
$$(10011101011.001)_{2}\implies 1.00111010110001 \times 2^{10}$$
$$E-127 = 10$$
$$ E = 130 $$
$$ E = (130)_{10}$$
$$ E = (10000010)_2$$
 - $E=10+127=137\to(10001001)_2$
 - $M=00111010110001000000000$
 - $S=0$
 - $0\ 10001001\ 00111010110001000000000$

 For Double Precision
 Compare with Equation 
 $$ E - 1023 = 10 $$
 $$ E = 1033 = (100000010001)_{2} $$
 - $E = 10 + 1023 = 1033 \to (10000001001)_2$
 - $M = 00111010110001000000000$
 - $S = 0$

| S   | E   | M   |
| --- | --- | --- |
|     |     |     |
### Question 2
$(263.3)_{10}$

- $(263)_{10}\to(100001111)_2$
- $(0.3)_10\to(00100111\dots)_{2}$

Compare with Equation
$$100001111.01010101\dots$$

$$1.0000111101010101 \dots \times 2^8$$

Comparing

$$ E= 8+127 $$
$$ E = 135 $$

$$ (E)_{2} = (10000111)_{2}$$
$$E$$

| S   | E          | M   |
| --- | ---------- | --- |
| 0   | 0b10000111 | ... |

## Question 3
$$-786.25$$

### Solution
- $(786)_{10}=(1100010010)_{2}$
- $(0.25)_{10}=(01)_{2}$
- $1100010010.01=1.10001001001*10^9$
- $$\pm (1.N) \times 2^{n+127} \text{    because  Negative Bit } $$
- E = 136


| S   | E          | M             |
| --- | ---------- | ------------- |
| 1   | 0b10001000 | 0b10001001001 |
###### Information
- date: 2025.03.06
- time: 16:11