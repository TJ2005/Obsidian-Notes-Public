---
Title: Computer Organization and Architecture Lecture 6
Status: 
marker: 
tags: 
Date: 2025.01.16
Time: 11:09
---
Continued from [[Computer Organization and Architecture Lecture 5]]
# Parameterizing Processes
We have two crucial things required for a process to be executed.
- Data/Memory
- Instructions
Now there are two methods or ways to do the storing part of this process
We have buses for the process of moving data
In computer architecture, the **Control Bus**, **Data Bus**, and **Address Bus** are key components that facilitate communication between the CPU, memory, and I/O devices. Each has a distinct role in the system:

---
### 1. **Address Bus**
- **Purpose**: Transmits memory or I/O addresses from the CPU to other components.
- **Direction**: Unidirectional (from CPU to memory or I/O).
- **Width**: Determines the maximum addressable memory or I/O locations.
    - For example, a 32-bit address bus can address 2322^{32} locations.
### 2. **Data Bus**
- **Purpose**: Transfers actual data between the CPU, memory, and I/O devices.
- **Direction**: Bidirectional (data can flow to or from the CPU).
- **Width**: Determines the amount of data transferred simultaneously.
    - For instance, a 64-bit data bus can transfer 64 bits (8 bytes) in one cycle.
### 3. **Control Bus**
- **Purpose**: Carries control signals to coordinate and manage various operations within the system.
- **Direction**: Both unidirectional and bidirectional, depending on the signal type.
- **Key Signals**:
    - **Read/Write (R/W)**: Indicates whether data is being read from or written to memory/I/O.
    - **Clock Signals**: Synchronize operations.
    - **Interrupt Signals**: Alert the CPU of external events.
    - **Bus Request/Grant**: Manage access to the bus.

---

### Summary of Differences

|**Bus Type**|**Direction**|**Purpose**|**Key Characteristics**|
|---|---|---|---|
|Address Bus|Unidirectional|Transmits memory or I/O addresses.|Width determines the addressable range.|
|Data Bus|Bidirectional|Transfers data between CPU, memory, and I/O.|Width affects data transfer speed and size.|
|Control Bus|Both|Sends control signals for coordination.|Manages read/write, interrupts, and bus arbitration.|

---

By working together, these buses enable efficient communication in a computer system, ensuring that data and instructions flow where they are needed.

![[IMG-20250730000528756.png|300]]
### **Harvard Architecture**

In the **Harvard Architecture**, the memory for program instructions and data is physically separate, with dedicated buses for each. This eliminates the bottleneck seen in the Von Neumann architecture.

---

### Key Features of Harvard Architecture:
1. **Separate Memory Spaces**:
    - Instructions and data are stored in **different memory locations**, with independent address spaces.
    - Instructions are fetched from **instruction memory**, and data is fetched from **data memory**.
2. **Parallel Operation**:
    - The CPU can fetch instructions and data simultaneously due to separate buses for each.
    - This increases execution speed and efficiency.
3. **Bus Operations**:
    - **Instruction Bus**: Carries instruction memory addresses and retrieved instructions.
    - **Data Bus**: Handles data memory addresses and fetched/stored data.

---

### **Pros and Cons of Von Neumann Architecture**
#### **Pros**:
1. **Simplicity**: A single memory space and unified buses make the architecture easier to implement and manage.
2. **Flexibility**: Code and data can be dynamically interchanged since they share the same memory.
3. **Cost-Effective**: Requires fewer physical components, reducing hardware complexity and cost.

#### **Cons**:
1. **Von Neumann Bottleneck**: The single bus creates a communication bottleneck, limiting performance.
2. **Sequential Access**: Instructions and data cannot be accessed simultaneously, slowing execution speed.
3. **Security Risks**: Storing code and data together increases the risk of malicious code execution or memory corruption.

---

### **Pros and Cons of Harvard Architecture**
#### **Pros**:
1. **Increased Speed**: Parallel access to instructions and data reduces execution time.
2. **Reduced Bottleneck**: Separate buses eliminate the communication bottleneck.
3. **Enhanced Security**: Segregated instruction and data memory reduce risks of memory corruption or code injection.

#### **Cons**:
1. **Complexity**: Requires separate memory units and buses, increasing design complexity.
2. **Cost**: Additional components make the system more expensive to implement.
3. **Less Flexible**: Instructions and data are strictly separated, reducing the ability to use memory dynamically.

---

### **Difference Table: Von Neumann vs. Harvard Architecture**

|**Feature**|**Von Neumann Architecture**|**Harvard Architecture**|
|---|---|---|
|**Memory Structure**|Shared memory for instructions and data.|Separate memory for instructions and data.|
|**Bus Structure**|Single bus for both instructions and data.|Separate buses for instructions and data.|
|**Data and Instruction Fetch**|Sequential (one at a time).|Parallel (simultaneous fetch possible).|
|**Speed**|Slower due to sequential access.|Faster due to parallel operation.|
|**Hardware Complexity**|Simpler, with fewer components.|More complex due to separate memory and buses.|
|**Cost**|Cheaper to implement.|More expensive.|
|**Flexibility**|Instructions and data can be interchanged.|Instructions and data are strictly segregated.|
|**Bottleneck**|Prone to the Von Neumann bottleneck.|No bottleneck due to separate pathways.|

---

### **Conclusion**
The Von Neumann architecture provides simplicity and cost-effectiveness, making it suitable for general-purpose computing. In contrast, the Harvard architecture offers enhanced speed and efficiency, often used in specialized systems like microcontrollers and embedded devices. The choice between the two depends on the system requirements for performance, cost, and complexity.
# Parallel Processing
![[IMG-20250730000539718.png|center|400]]

# Flynn's Classification
- ### Four Major Groups
	- SISD
		- Single Instruction stream
		- Single Data Stream
	- SIMD
		- Single Instruction stream
		- Multiple Data stream
	- MISD
		- Multiple Instruction stream
		- Single data stream
	- MIMD
		- Multiple Instructions stream
		- Multiple stream
![[IMG-20250730000600554.png|center|400]]

![[IMG-20250730000609498.png]]
# References
Continued to [[Computer Organization and Architecture Lecture 7]]
###### Information
- date: 2025.01.16
- time: 11:09