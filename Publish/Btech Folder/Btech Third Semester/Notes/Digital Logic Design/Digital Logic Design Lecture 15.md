---
Title: Digital Logic Design Lecture 15
Status: 
marker: 
tags: 
Date: 2024.09.24
Time: 10:27
---

---
**Note on Half Adder and Full Adder Using Multiplexer (MUX):**

1. **Half Adder**:
   - A half adder is a fundamental digital circuit that performs the addition of two single-bit binary numbers.
   - The half adder has two outputs: 
     - Sum (S) = A XOR B
     - Carry (C) = A AND B
   - The truth table displayed shows the possible outcomes for different input values of A and B.

2. **Full Adder**:
   - A full adder extends the half adder by adding an additional carry-in input (Cin), allowing for the addition of three bits (A, B, Cin).
   - The outputs are:
     - Sum (S) = (A XOR B) XOR Cin
     - Carry (C) = (A AND B) OR (Cin AND (A XOR B))
   - The full adder can be implemented using multiple half adders or by utilizing a multiplexer (MUX) for efficiency in logic design.

3. **Multiplexer (MUX)**:
   - A 4:1 multiplexer (4-input, 1-output) can be used to implement logical functions by selecting between different input lines based on select signals (A, B).
   - In this context, the MUX is being used to combine the results from the half adder and full adder operations, routing the necessary logic for the outputs.

---

This note provides a concise summary of the topic discussed in the class based on the whiteboard content seen in the image

# References


###### Information
- date: 2024.09.24
- time: 10:27>)