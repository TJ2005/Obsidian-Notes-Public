---
Title: Digital Logic Design Lecture 8
Status: 
marker: 
tags: 
Date: 2024.08.08
Time: 08:32
---
# Digital Logic Design Lecture 8

## Main Note

### Boolean Algebraic Theorems

In Boolean algebra, certain theorems help simplify and analyze Boolean expressions, similar to algebraic theorems in traditional mathematics. These theorems are foundational for understanding and manipulating digital logic circuits.

| Theorem Number | Theorem                                                  | Description                                                                                                           |
| -------------- | -------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| 1.1            | \( A + 0 = A \)                                          | The identity law for addition. Adding 0 to any variable \( A \) leaves \( A \) unchanged.                             |
| 1.2            | \( A \cdot 1 = A \)                                      | The identity law for multiplication. Multiplying any variable \( A \) by 1 leaves \( A \) unchanged.                  |
| 1.3            | \( A + 1 = 1 \)                                          | The domination law for addition. Adding 1 to any variable \( A \) results in 1.                                       |
| 1.4            | \( A \cdot 0 = 0 \)                                      | The domination law for multiplication. Multiplying any variable \( A \) by 0 results in 0.                            |
| 1.5            | \( A + A = A \)                                          | The idempotent law for addition. Adding a variable \( A \) to itself results in \( A \).                              |
| 1.6            | \( A \cdot A = A \)                                      | The idempotent law for multiplication. Multiplying a variable \( A \) by itself results in \( A \).                   |
| 1.7            | \( A + \overline{A} = 1 \)                               | The complement law for addition. A variable \( A \) OR-ed with its complement \( \overline{A} \) results in 1.        |
| 1.8            | \( A \cdot \overline{A} = 0 \)                           | The complement law for multiplication. A variable \( A \) AND-ed with its complement \( \overline{A} \) results in 0. |
| 1.9            | \( \overline{A + B} = \overline{A} \cdot \overline{B} \) | De Morgan's theorem for addition. The complement of a sum is the product of the complements.                          |
| 1.10           | \( \overline{A \cdot B} = \overline{A} + \overline{B} \) | De Morgan's theorem for multiplication. The complement of a product is the sum of the complements.                    |
|                |                                                          |                                                                                                                       |


### Truth Table to Prove Theorems

To validate the Boolean theorems, truth tables can be used. Below are truth tables for some of the key theorems:

1. **Theorem 1.1: \( A + 0 = A \)**

| \( A \) | \( 0 \) | \( A + 0 \) |
| ------- | ------- | ---------- |
| 0       | 0       | 0          |
| 1       | 0       | 1          |

2. **Theorem 1.2: \( A \cdot 1 = A \)**

| \( A \) | \( 1 \) | \( A \cdot 1 \) |
| ------- | ------- | -------------- |
| 0       | 1       | 0              |
| 1       | 1       | 1              |

3. **Theorem 1.3: \( A + 1 = 1 \)**

| \( A \) | \( 1 \) | \( A + 1 \) |
| ------- | ------- | ---------- |
| 0       | 1       | 1          |
| 1       | 1       | 1          |

4. **Theorem 1.4: \( A \cdot 0 = 0 \)**

| \( A \) | \( 0 \) | \( A \cdot 0 \) |
| ------- | ------- | -------------- |
| 0       | 0       | 0              |
| 1       | 0       | 0              |

5. **Theorem 1.7: \( A + \overline{A} = 1 \)**

| \( A \) | \( \overline{A} \) | \( A + \overline{A} \) |
| ------- | ------------------ | --------------------- |
| 0       | 1                  | 1                     |
| 1       | 0                  | 1                     |

6. **Theorem 1.8: \( A \cdot \overline{A} = 0 \)**

| \( A \) | \( \overline{A} \) | \( A \cdot \overline{A} \) |
| ------- | ------------------ | ------------------------ |
| 0       | 1                  | 0                        |
| 1       | 0                  | 0                        |

7. **De Morgan's Theorems**

   **De Morgan's First Theorem:**


   | \( A \) | \( B \) | \( A + B \) | \( \overline{A + B} \) | \( \overline{A} \) | \( \overline{B} \) | \( \overline{A} \cdot \overline{B} \) |
   | ------- | ------- | ----------- | --------------------- | ---------------- | ---------------- | ----------------------------- |
   | 0       | 0       | 0           | 1                     | 1                | 1                | 1                             |
   | 0       | 1       | 1           | 0                     | 1                | 0                | 0                             |
   | 1       | 0       | 1           | 0                     | 0                | 1                | 0                             |
   | 1       | 1       | 1           | 0                     | 0                | 0                | 0                             |

   **De Morgan's Second Theorem: \( \overline{A \cdot B} = \overline{A} + \overline{B} \)**

   | \( A \) | \( B \) | \( A \cdot B \) | \( \overline{A \cdot B} \) | \( \overline{A} \) | \( \overline{B} \) | \( \overline{A} + \overline{B} \) |
   | ------- | ------- | --------------- | ----------------------- | ---------------- | ---------------- | ----------------------------- |
   | 0       | 0       | 0               | 1                       | 1                | 1                | 1                             |
   | 0       | 1       | 0               | 1                       | 1                | 0                | 1                             |
   | 1       | 0       | 0               | 1                       | 0                | 1                | 1                             |
   | 1       | 1       | 1               | 0                       | 0                | 0                | 0                             |

### References

- Digital Logic Design by M. Morris Mano
- Introduction to Logic Design by Alan B. Marcovitz
- Boolean Algebra and Logic Circuits by J. P. Tremblay and R. Manohar

###### Information
- Date: 2024.08.08
- Time: 08:32

---

