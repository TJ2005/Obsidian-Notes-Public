---
Title: "Computer Organization and Architecture Lecture 18"
Status: 
marker: 
tags: 
Date: "2025.03.10"
Time: "14:18"
---
# Computer Organization and Architecture Lecture 18

## Human Memory vs. Computer Memory

### Key Questions:
- Is human memory similar to computer memory?
- How does the brain store and retrieve information?
- What role does the hippocampus play in memory formation?
- How does the brain process information?

### Human Memory and Information Processing

- **Storage and Retrieval:** The brain uses neural networks to store and retrieve information.
- **Sequential Memory:** Stores and retrieves information in a specific order.
- **Hippocampus Role:** Crucial for converting short-term to long-term memories.
- **Information Processing:** Dynamic and adaptive, using sensory input and neural networks.

### Conclusion
The brain's complex neural networks and structures like the hippocampus make it unique compared to computer memory. Understanding these processes provides insights into memory formation and maintenance.

# Serial Adder
This diagram illustrates the process of bit-by-bit addition using a Full Adder (FA) in digital circuits.

## Components:

1. **Inputs:**
   - Two 4-bit binary numbers:
     - $A = [A_1, A_2, A_3, A_4]$
     - $B = [B_1, B_2, B_3, B_4]$

2. **Full Adder (FA):**
   - Takes two bits (one from each number) and performs binary addition.
   - Produces a sum bit and a carry bit.

3. **Process:**
   - **Bit 1 and Bit 2:** Individual bits from $A$ and $B$ are fed into the Full Adder.
   - **Shift:** The resulting sum and carry bits are shifted to form the output bits.

4. **Output:**
   - The result is a 4-bit binary number:
     - $S = [S_1, S_2, S_3, S_4]$

5. **Operation:**
   - The Full Adder performs bit-by-bit addition, handling both the sum and carry for each bit position.
   - The process ensures accurate binary addition, accounting for carries between bit positions.

This setup is fundamental in digital circuit design for performing arithmetic operations on binary numbers.

![[Serial Adder Using a single full adder.canvas|Serial Adder Using a single full adder]]

# Combinational and Sequential ALU
The Arithmetic Logic Unit (ALU) in a CPU can be designed using combinational and sequential logic circuits.
The standard IC's cannot solve ieee 754 floating point numbers. The ALU can be designed using combinational and sequential logic circuits.
The combinational ALU performs arithmetic and logic operations on the input data without storing any state information.

The arithmetic symbols is represented in a certain manner in diagrams for its a reason. The symbols are used to represent the arithmetic operations in the ALU.

- A and B are the input data.
- Status flags are the output data.
- The ALU performs the operation based on the control signals.


<div style="display: flex; justify-content: center;">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/0f/ALU_block.gif/1200px-ALU_block.gif" width="400">
</div>


# References



###### Information
- date: 2025.03.10
- time: 14:18