---
Title: Computer Organization & Architecture Lecture 4
Status: 
marker:
  - "[[Computer Architecture]]"
  - "[[Architecture]]"
  - "[[CPU]]"
  - "[[computers]]"
tags: 
Date: 2025.01.10
Time: 13:15
---
Earlier Lectures are missed due to my absence...
# **Computer Organization & Architecture**

**Lecture 4**

---
## **Memory Overview**

Memory in a computer system plays a vital role in storing data and instructions for processing. It can be categorized into:

- **Permanent Memory:** Retains data even when the system is powered off.
- **Temporary Memory:** Loses data when the system is powered off.

### **Types of Memory**
1. **Primary Memory**
    - **RAM (Random Access Memory):**  
        Volatile memory used to store data and programs actively being accessed by the CPU.
    - **ROM (Read-Only Memory):**  
        Non-volatile memory used for storing essential instructions like firmware. Data is permanent and cannot be easily modified.
    - **Cache Memory:**  
        High-speed memory located close to the CPU, designed to store frequently accessed data for faster processing.
2. **Secondary Memory**
    - **Hard Disk (HDD/SSD):**  
        Non-volatile storage for operating systems, applications, and user data.
    - **Optical Disk (CD/DVD/Blu-ray):**  
        Used for data distribution and backup.

---

## **CPU Representation**
A **CPU** is the core component of a computer responsible for processing data and performing operations. To function effectively, the CPU relies on memory to store both data and instructions.

### **Importance of Memory Proximity**
The distance between the memory and the CPU significantly impacts processing times, as modern CPUs deal with extremely fast processing cycles measured in 10−n10^{-n} seconds.

### **Analogy: Manufacturing Unit**

- **Warehouse:** Represents secondary memory (e.g., hard disks). Stores all the material (data) but is far from the processing unit (CPU).
- **Outer Storage Area:** Represents RAM. Brings chunks of material closer to the manufacturing unit for accessibility.
- **Factory Boxes:** Represents cache memory. The smallest, closest, and fastest storage used by machines (CPU).

When a specific raw material (data) is needed:

1. The factory (CPU) checks the boxes (cache memory) first.
2. If the material is not in the boxes (cache miss), it looks in the outer storage (RAM).
3. If found in RAM, the material is moved to the boxes (cache) and processing resumes.
4. If not found in RAM, it fetches from the warehouse (secondary memory), which takes more time.

### **Cache Hit & Miss**
- **Cache Hit:** When the requested data is found in the cache.
- **Cache Miss:** When the requested data is not found in the cache, requiring retrieval from slower memory levels.

![[IMG-20250730000528754.png]]

## Memory Unit
- Storage area in which the programs are kept which are running
- RAM
- Cache Memory 
	- Highly Coupled
	- non volatile

## **Arithmetic & Logical Unit (ALU)**

The Arithmetic and Logical Unit (ALU) is a crucial component of the CPU, responsible for performing arithmetic and logical operations required during processing.

### **Key Functions of the ALU**

1. **Arithmetic Operations:**
    - Basic operations such as addition, subtraction, multiplication, and division.
2. **Logical Operations:**
    - Operations like AND, OR, NOT, XOR, and comparisons (e.g., greater than, less than, equal to).
3. **Shifting Operations:**
    - Shifting bits left or right for tasks like multiplication or division by powers of 2.

### **Design of ALUs**

- The ALU is constructed using **Logical Units**, as discussed in [[Digital Logic Design]].
- **Logical Units** are designed using transistor arrangements that implement logic gates like AND, OR, and NOT.
- Transistor technologies such as CMOS or FinFET are often used in these designs.

---

## **Control Unit (CU)**
The Control Unit (CU) acts as the manager of the CPU, directing the flow of data and instructions between the CPU, memory, and input/output devices.

### **Key Functions of the Control Unit**

1. **Instruction Fetching:**
    - Retrieves instructions from memory.
2. **Decoding Instructions:**
    - Interprets the instructions to determine what actions are required.
3. **Execution Coordination:**
    - Directs the ALU and other CPU components to perform tasks.
4. **Data Flow Control:**
    - Ensures that data moves efficiently between memory and processing units.

### **Types of Control Units**

1. **Hardwired Control Unit:**
    - Uses fixed logic circuits to control signals.
    - Faster but less flexible.
2. **Microprogrammed Control Unit:**
    - Uses a set of instructions (microinstructions) stored in a special memory.
    - More flexible but slightly slower.

---

## **Output Unit**
The Output Unit is responsible for conveying the results of processing to the user or another system.

### **Key Functions of the Output Unit**
1. **Data Conversion:**
    - Converts the binary data processed by the CPU into human-readable formats (e.g., text, graphics).
2. **Interface with External Devices:**
    - Communicates with peripherals like monitors, printers, and storage devices.
3. **Error Reporting:**
    - Displays errors or exceptions encountered during processing.

---

By combining the ALU, Control Unit, and Output Unit, the CPU can perform a wide range of tasks efficiently, ensuring seamless data processing and communication with other components.

---
## **References & Extras**
Finfets
### Loops 
[[Loops Management in Computer Architecture]]
Also discover JUMPS.

### Ram Types
SRAM & DRAM

- **Date:** 2025-01-10
- **Time:** 13:15
- Continued to [[Computer Organization and Architecture Lecture 5]]

---