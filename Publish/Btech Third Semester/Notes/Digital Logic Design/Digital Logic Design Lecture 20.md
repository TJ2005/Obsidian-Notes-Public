---
Title: Digital Logic Design Lecture 20
Status: 
marker: 
tags: 
Date: 2024.10.15
Time: 13:10
---
### Sequential Logic Circuits

Sequential logic circuits are circuits whose output depends not only on the present input but also on the history of the input, making them different from combinational logic circuits. Registers are key components of sequential logic, used to store binary data and perform shift operations.

## Registers

A **register** is a group of flip-flops, each capable of storing one bit of information. A register can store multivalued bit information (i.e., more than one bit) and is used for temporary data storage, data transfer, and data manipulation in digital systems.

- **Flip-flop vs Register**: The main difference between a flip-flop and a register is that a **flip-flop** stores only a single bit of information, while a **register** is a collection of flip-flops and can store multiple bits.

- Data in **serial** form is referred to as **temporal code** because bits are transferred one after another over time.
- Data in **parallel** form is referred to as **spatial code**, as bits are transferred simultaneously over multiple lines.

### Types of Registers

There are four primary types of registers based on how data is input and output:

1. **SISO (Serial In Serial Out)**: Data is input and output in serial form.
2. **SIPO (Serial In Parallel Out)**: Data is input serially and output in parallel.
3. **PISO (Parallel In Serial Out)**: Data is input in parallel and output serially.
4. **PIPO (Parallel In Parallel Out)**: Data is input and output in parallel form.

---

### Shift Registers

Shift registers are a special type of register where data is shifted either to the right or left as new bits are introduced. These are primarily used for data transfer and manipulation in digital circuits.

- **Right Shift Register**: Data is shifted one bit to the right for every clock cycle.
- **Left Shift Register**: Data is shifted one bit to the left for every clock cycle.
- **Bidirectional Shift Register**: Data can be shifted both to the right and left based on the control signal.

#### Universal Shift Register

A **universal shift register** is a versatile register that can perform all of the following operations:
- Shift left
- Shift right
- Load parallel data
- Output data in parallel or serially

This makes the universal shift register very useful in digital systems where data manipulation and transfer are needed in multiple forms.

---

### Visual Representation of Shift Registers

#### 1. **SISO (Serial In Serial Out)**
```plaintext
Input -> [D] -> [D] -> [D] -> [D] -> Output
```
Data enters one bit at a time from the left, and after shifting through the flip-flops, exits one bit at a time from the right.

#### 2. **SIPO (Serial In Parallel Out)**
```plaintext
Input -> [D] -> [D] -> [D] -> [D]
                  |     |     |
                Q3    Q2    Q1
```
Data enters serially, and after all bits are input, the output is taken in parallel from each flip-flop.

#### 3. **PISO (Parallel In Serial Out)**
```plaintext
 Q3    Q2    Q1    Q0
  |     |     |     |
 [D] <- [D] <- [D] <- [D] <- Output
```
Data is loaded in parallel into the flip-flops and shifted out serially one bit at a time.

#### 4. **PIPO (Parallel In Parallel Out)**
```plaintext
 Q3    Q2    Q1    Q0
  |     |     |     |
 [D]   [D]   [D]   [D]
  |     |     |     |
 Output Output Output Output
```
Data is loaded in parallel and output in parallel simultaneously.

---

### Visual Representation of Shift Register Operations

#### Right Shift Register
```plaintext
Input -> [D] -> [D] -> [D] -> [D] -> Output
         ^                          ^
         |---Data is shifted to the right---|
```

#### Left Shift Register
```plaintext
Output <- [D] <- [D] <- [D] <- [D] <- Input
         ^                          ^
         |---Data is shifted to the left---|
```

#### Bidirectional Shift Register
```plaintext
         (Right Shift)         (Left Shift)
Input -> [D] -> [D] -> [D] <- [D] <- Output
         |---Shift Right---|   |---Shift Left---|
```

#### Universal Shift Register
```plaintext
          Parallel In/Out
 Q3    Q2    Q1    Q0
  |     |     |     |
 [D] <- [D] <- [D] <- [D]
 |----Shift Left or Right---|
```
- Can shift both left and right.
- Can load and output data in parallel.

---

### Applications of Shift Registers

- **Data Storage**: Registers store temporary data in digital circuits.
- **Data Transfer**: Shift registers are used to transfer data serially or in parallel between different components of a system.
- **Serial-to-Parallel and Parallel-to-Serial Conversion**: Shift registers are used to convert between serial and parallel data formats.
- **Counters**: Shift registers can function as counters in specific digital circuits.
- **Digital Signal Processing (DSP)**: Used in DSP for manipulating data streams, signal storage, and more.

By using these different types of registers and shift operations, various types of data manipulation and storage tasks are efficiently handled in digital systems.