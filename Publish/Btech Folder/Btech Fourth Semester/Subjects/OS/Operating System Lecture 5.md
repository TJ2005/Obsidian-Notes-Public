---
Title: Operating System Lecture 7
Status: 
marker: 
tags: 
Date: 2025.01.18
Time: 12:02
---
# Unit 2
## Content
- Processes
- Thread Definition
- Process Scheduling
# Process
Operating system executes a variety of programs that run as a processes.
A process may include:
- Identifier
- Code
- Memory
	- Code, Data, Stack
- Registers
	- Program Counter, Stack Pointer Flags,
- Other Data
	- States of Files
	- File access
- Not all the data that's associated with a process is given access to the process
#### Memory Representation of a process
The diagram below defines the representation of memory in a process.
1. **Text**: This section holds the executable code of the program. It's read-only and contains instructions that the CPU executes.
2. **Data**: This section contains global and static variables. These variables are initialized and their values are preserved throughout the lifetime of the program.
3. **Heap**: The heap is where dynamically allocated memory (via `malloc` or `new` in languages like C and C++) resides. Memory in the heap grows upward, meaning it starts from a low memory address and expands upwards as memory is allocated
4. **Stack**: The stack is used for function calls and local variables. It grows downward, meaning it starts from a higher memory address and grows downwards as new function calls are made. It stores return addresses, function parameters, and local variables.
5. **Max & 0**: These likely represent the maximum and minimum addresses of the memory. The stack grows downward (from the top), and the heap grows upward (from the bottom).
This memory layout ensures that different parts of the program (code, data, stack, and heap) are properly managed and isolated from one another. It also provides a structure that helps in memory management and avoids conflicts between different sections.


![[IMG-20250730000528868.png| center | 300]]

### Process States
A process can exhibit multiple states. 
- **New**: The process is being created
- **Running**: Instructions are being executed
- **Waiting**: The process is waiting for some event flag to appear/occur
- **Ready**: The process is in the prepared state where it can be assigned to a processor
- **Terminated** : Killed or finished execution

![[IMG-20250730000546465.png|center|400]]

# References


###### Information
- date: 2025.01.18
- time: 12:02