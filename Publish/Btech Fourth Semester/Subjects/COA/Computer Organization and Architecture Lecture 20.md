---
Title: "Computer Organization and Architecture Lecture 20"
Status: 
marker: 
tags: 
Date: "2025.03.12"
Time: "09:41"
---
# Addressing Modes
Mode is nothing but a way of addressing the memory. There are different ways to address the memory. The different ways of addressing the memory are called addressing modes.
- Implied Mode
- Immediate Mode
- Register Mode

When memory size is 1mb we have $2^{20}$ locations. The memory has $20$ address bits. so its split into 4 parts. The first 4 bits are used to select the memory bank. The next 6 bits are used to select the row. The next 6 bits are used to select the column. The last 4 bits are used to select the word.

Instruction size can be 1,2,3,4 bytes long. The instruction size is 2 bytes long. Instruction queue can only store complete intructions. 
### BIU
- Instruction streaembyte queue
- A set of segment registers
- Instruction Pointer

If BIU has 6 bytes and 2,3 bytes instructions come and sit a 2 byte cant come to occupy.d


# References


###### Information
- date: 2025.03.12
- time: 09:41