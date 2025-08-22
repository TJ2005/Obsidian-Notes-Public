---
Title: Digital Logic Design Lecture 9
Status: 
marker: 
tags: 
Date: 2024.08.13
Time: 13:10
---
i# Digital Logic Design Lecture 9
This Lecture covers unit 2 beginning. and the index as follows

# Comparison between Analog and Digital systems
\![[Digital Logic Design Analogue and Digital Systems]]

# Symbols for Logical Operations

| Function           | Representation                 | Name                |
| ------------------ | ------------------------------ | ------------------- |
| **AND**            | $A \land B$ or $A \cdot B$     | AND Gate            |
| **OR**             | $A \lor B$ or $A + B$          | OR Gate             |
| **NAND**           | $\overline{A \land B}$         | NAND Gate           |
| **NOR**            | $\overline{A \lor B}$          | NOR Gate            |
| **XOR**            | $A \oplus B$                   | XOR Gate            |
| **XNOR**           | $\overline{A \oplus B}$        | XNOR Gate           |
| **NOT**            | $\overline{A}$                 | NOT Gate (Inverter) |
| **NAND (3-input)** | $\overline{A \cdot B \cdot C}$ | 3-Input NAND Gate   |
| **OR (3-input)**   | $A \lor B \lor C$              | 3-Input OR Gate     |
|                    |                                |                     |

# Types of Circuits
There are mostly two types of circuits that we will be covering in unit 2.
## **Combinational Circuits**

**Combinational circuits** are logic circuits where the output depends solely on the current inputs. They do not have memory or feedback loops, meaning the output is a direct function of the inputs at any given time. These circuits perform operations such as addition, subtraction, and encoding based on the input values.

**Key Characteristics:**

- **No Memory**: The output is purely a function of the current input values. There is no storage of previous input states.
- **Immediate Response**: The output changes as soon as the input changes, reflecting the combinational logic of the circuit.

**Components**
1. Set of statements
2. Boolean expression 
3. Truth Table
## **Sequential Circuits**

**Sequential circuits** are logic circuits where the output depends on both the current input and the history of inputs. This means they have memory elements like flip-flops or latches to store previous states. The output is a function of the current inputs and the stored state.

**Key Characteristics:**

- **Memory**: Sequential circuits have memory elements that store information about past inputs or states.
- **Clock-Driven**: Many sequential circuits are synchronized with a clock signal that controls when the memory elements are updated.

# Simplification of the Boolean Functions
1. Algebraic Method
2. Karnaughh-map technique ( K-Map )
3. Quine McCluskey Method and
4. Variable entered mapping

## Algebraic Method
For example 
$$
Y = (A + BC)(B + \overline{C}A)
$$
$$
Y = A \cdot (B + \overline{C}A) + BC \cdot (B + \overline{C}A)
$$
$$
Y = A \cdot B + A \cdot \overline{C}A + BC \cdot (B + \overline{C}A)
$$
$$
Y = A \cdot B + A \cdot \overline{C} + BC \cdot B + BC \cdot \overline{C}A
$$
$$
Y = A \cdot B + A \cdot \overline{C} + BC
$$
### Product of Sums (POS)

Consider the Boolean function \( F(A, B, C) \) which can be represented in the POS form as follows:

$$
F(A, B, C) = (\overline{A} + \overline{B} + \overline{C})(A + B + C)
$$

### Sum of Products (SOP)

Consider the Boolean function \( F(A, B, C) \) which can be represented in the SOP form as follows:

$$
F(A, B, C) = \overline{A}BC + AB \overline{C}
$$

## Basic Logic Operation using NAND Gate
![Image](https://www.electronics-tutorials.ws/wp-content/uploads/2019/09/log80.gif)

# Unindexed
## Digital Signal Representation
### Positive Logic
Using a high signal for high ( Binary 1 ) and low voltage for low signal ( Binary 2 ).
### Negative Logic
Using a low signal for high ( Binary 1 ) and high voltage for low ( Binary 2 ).

# References


###### Information
- date: 2024.08.13
- time: 13:10