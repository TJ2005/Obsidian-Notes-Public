---
Title: Storage Algorithm
Status: 
marker: 
tags: 
Date: 2024.08.09
Time: 23:29
---
Files are saved in memory registers as a series of [[bytes]]. The [[operating system]] and file system manage how these bytes are allocated in memory. The data is stored in binary format, with each byte consisting of 8 bits. The sequence and structure of these bytes depend on the file format and the architecture of the system (such as little-endian or big-endian).

### Bits, Bytes, and Nibbles
- **Bit:** The smallest unit of data in a computer, represented by a 0 or 1.
- **Nibble:** A group of 4 bits. It can represent 16 different values (0-15).
- **Byte:** A group of 8 bits. It can represent 256 different values (0-255).

For example:
- A single bit can be 0 or 1.
- A nibble can be `1010` (which is 10 in decimal).
- A byte can be `11001010` (which is 202 in decimal).

### LSB, MSB
- **LSB (Least Significant Bit):** The bit with the lowest value in a binary number, located at the far right. It holds the least weight (2^0).
- **MSB (Most Significant Bit):** The bit with the highest value in a binary number, located at the far left. It holds the most weight (2^(n-1) for an n-bit number).