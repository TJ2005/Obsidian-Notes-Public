---
Title: "Memory Hierarchy"
Status: 
marker: 
tags: 
Date: "2025.03.16"
Time: "23:28"
---
# Characteristics of Memory Systems

| Characteristic             | Description                                                    |
|----------------------------|----------------------------------------------------------------|
| [[#1) **Location**]]        | The physical location of memory in the system.                |
| [[#2) **Capacity**]]        | The size of memory and how much it can store.                  |
| [[#3) **Unit of Transfer**]]| The number of bits transferred at a time.                    |
| [[#4) **Access Method**]]   | The method used to access the memory.                         |
| [[#5) **Performance**]]     | Memory performance parameters: access time, cycle time, transfer rate. |
| [[#6) **Physical Type**]]   | The type of physical memory used.                            |


---

### 1) **Location**
The **location** of memory refers to where in the system the memory resides. The memory could be located in various parts of the system:

- **CPU**: Registers and internal cache memory are located within the CPU. They are very fast, but they have very limited storage capacity.
- **Internal**: This is the main memory (RAM) that the CPU can directly access. It is larger than CPU memory but slower.
- **External**: This refers to secondary storage like magnetic disks or tapes, which are far from the CPU and slower to access.

**Ideal characteristic**: Memory located inside or near the CPU (like registers or cache) provides the fastest access times.
**Unideal characteristic**: Memory located far from the CPU (such as secondary storage) has slower access times, which leads to delays.

---

### 2) **Capacity**
**Capacity** refers to the total amount of data the memory can store. Memory capacity is typically expressed in terms of word size and the number of words available.

- **Word size**: The unit of data that memory can handle at a time (e.g., 8, 16, or 32 bits).
- **Number of words**: Specifies how many words the memory can hold. For example, a system with 4K × 8 memory would have a word size of 8 bits and a total of 4096 words.

**Ideal characteristic**: Sufficient capacity to store data for all tasks without overloading the memory system.
**Unideal characteristic**: Too little capacity can cause performance degradation, such as frequent memory swapping or running out of space.

---

### 3) **Unit of Transfer**
The **unit of transfer** is the maximum number of bits that can be read from or written to the memory at once. This term is critical because it affects the speed of memory operations.

- **In main memory**, the unit of transfer is usually equal to the word size.
- **In external memory**, the unit of transfer might be larger than the word size, often referred to as "blocks".

**Ideal characteristic**: A larger unit of transfer allows for faster memory operations, as it reduces the overhead associated with multiple read/write operations.
**Unideal characteristic**: Smaller units of transfer result in slower performance, as more operations are needed to transfer the same amount of data.

---

### 4) **Access Method**
The **access method** defines how the data in memory is retrieved or written. The two most common types of access methods are:

- **Sequential access**: Data is accessed in a specific order. To access data at position N, you must first access all previous records. A tape drive is an example.
- **Random access**: Each addressable location in memory has a unique address, allowing data to be accessed directly without needing to go through previous locations.

**Ideal characteristic**: **Random access** is ideal as it allows quick access to any memory location, reducing delays.
**Unideal characteristic**: **Sequential access** is less efficient because it requires reading through data sequentially, which slows down the process, especially when accessing random data.

---

### 5) **Performance**
**Performance** of the memory system is influenced by three main parameters: 

- **Access time**: This is the time taken by memory to complete a read/write operation. Faster memory like RAM has lower access times.
- **Memory cycle time**: This is the time required for memory to complete a cycle of read/write operations. For random access memory, it includes the access time plus any additional time needed before another access can occur.
- **Transfer rate**: This defines the speed at which data can be transferred in or out of the memory.

**Ideal characteristic**: High performance memory with fast access times, fast cycle times, and high transfer rates.
**Unideal characteristic**: Low performance memory, which has slow access times and low transfer rates, significantly reduces system speed.

---

### 6) **Physical Type**
The **physical type** of memory refers to the medium used for storing data, which affects the overall performance and cost. There are two major types of physical memory:

- **Semiconductor memory**: This is the most commonly used memory type (e.g., DRAM and SRAM) for main memory due to its high speed and reliability.
- **Magnetic storage**: This includes hard drives and tapes, which are slower than semiconductor memory but offer larger capacities at lower cost.

- **Volatile** vs **Non-volatile**: Volatile memory loses data when powered off, while non-volatile memory retains data.
- **Erasable** vs **Non-erasable**: Erasable memory can be written over, while non-erasable memory cannot be modified once written.

**Ideal characteristic**: **Semiconductor memory**, especially non-volatile memory, provides a good balance of speed, reliability, and capacity.
**Unideal characteristic**: **Magnetic or optical storage** tends to be slower, and **non-erasable memory** can limit flexibility and performance.

---

### Conclusion:
The characteristics of memory systems play a crucial role in determining the overall performance of a computer system. Balancing speed, size, and access methods ensures that memory operates efficiently. Memory hierarchy and optimization are essential in achieving the ideal memory performance.


| Technology             | Storage     | Access Method | Alterability | Performance | Typical Access Time (tᵃ) |
|------------------------|-------------|---------------|--------------|-------------|--------------------------|
| Semiconductor RAM       | Electronic  | Random        | Read/write   | Volatile    | 10 ns                    |
| Semiconductor ROM       | Electronic  | Random        | Read only    | Non-volatile| 10 ns                    |
| Magnetic (Hard) Disk    | Magnetic    | Semi-random   | Read/write   | Non-volatile| 50 ns                    |
| Optical Disk (CD-ROM)   | Optical     | Semi-random   | Read only    | Non-volatile| 100 ms                   |
| Erasable Optical Disk   | Optical     | Semi-random   | Read/write   | Non-volatile| 100 ms                   |
| Magnetic Tape           | Magnetic    | Serial        | Read/write   | Non-volatile| 1 s (Depends on access location) |



<center> <img width=400px src="https://www.cs.swarthmore.edu/~kwebb/cs31/f18/memhierarchy/figures/MemoryHierarchy.png"></img> 
# Characteristics of Memory Systems

### Key Considerations for Memory Systems:

- **Ideal memory characteristics**: 
    - Memory should ideally be **fast**, **large**, and **inexpensive**. These factors ensure high performance, ample storage, and affordable cost.
  
- **Challenges**:
    - Unfortunately, it is impossible to meet all three of these requirements simultaneously. 
    - **Increased speed** and **larger size** are typically achieved at the cost of **higher price**.
  
- **Fast Memory Systems**:
    - A **very fast memory system** can be achieved if **SRAM chips** (Static RAM) are used. These chips are much faster but have the disadvantage of being more expensive.

- **Expensive SRAM Chips**:
    - **SRAM chips** are costly and it becomes impractical to build large main memory systems using SRAM due to its high cost.

- **Alternative**:
    - The only alternative for building large main memories is to use **DRAM (Dynamic RAM)** chips, which are slower but more affordable than SRAM.
  
---

### Performance Implications:
- **Processor Fetching Data**:
    - The processor fetches code and data from main memory to execute the program. Since **DRAM**, which forms the main memory, is slower, it requires optimization to compensate for slower access.

- **Insertion of Wait States**:
    - **Wait states** are inserted into memory read/write cycles because **DRAM** is slower.
    - These wait states increase the total time needed to access data, which reduces the overall execution speed.

- **Solution**:
    - To overcome the performance bottleneck, most computer programs work with **small sections** of code and data at any particular time. This helps in reducing the impact of slower memory access.

---

### Summary:
Memory systems need to balance between being **fast**, **large**, and **inexpensive**. **SRAM** is ideal for speed but is too expensive for large memory systems. In contrast, **DRAM** is more affordable and suitable for large memories, though slower, requiring techniques like **wait states** to manage slower memory access.
# Characteristics of Memory Systems

### Key Points:

1. **Cache Memory**:
   - In modern memory systems, a small section of **SRAM** (Static RAM) is added alongside the main memory and is referred to as **cache memory**.
   - Cache memory is significantly faster than main memory and is used to store frequently accessed data to speed up the system.
   - **Program (code)** and **data** that are actively in use at any given time are usually accessed from **cache memory**.
   - This is accomplished by loading the active portion of the code and data from **main memory** into **cache memory**.

2. **Cache Controller**:
   - The **cache controller** manages the swapping of data between **main memory** and **cache memory** with the help of the **DMA controller** (Direct Memory Access).
   - The cache controller ensures that only the most relevant data remains in cache memory for quick access, improving overall performance.

3. **Types of Cache**:
   - The **cache memory** discussed earlier is referred to as **secondary cache**. 
   - Recent processors feature built-in cache memory known as **primary cache**, which is even faster and is integrated directly into the CPU.

4. **Role of DRAM and Cache**:
   - **DRAM** (Dynamic RAM) alongside **cache** allows for main memory systems in the range of tens of megabytes to be implemented at a **reasonable cost**.
   - This combination offers **better speed performance** while balancing memory size and cost.

5. **Memory Size Limitations**:
   - Despite these optimizations, the overall **size of memory** is still relatively small when compared to the demands of **large programs** that require massive amounts of data storage.
   - As programs grow in complexity and size, the need for larger memory systems increases, which is not always achievable with DRAM alone.

6. **Solution with Secondary Storage**:
   - A solution to this problem is to use **secondary storage**, which includes technologies like **magnetic disks** and **magnetic tapes**.
   - These forms of secondary storage can implement **larger memory spaces**, allowing for the storage of large volumes of data, although they are slower than primary memory.

### Summary:
- **Cache memory** speeds up data access by storing frequently used information, and **SRAM** is used due to its fast access times.
- **Cache controllers** ensure that data is efficiently swapped between **main memory** and **cache**.
- **DRAM** allows for reasonably priced, large main memory systems, but it is still not large enough to meet the needs of very large programs.
- To deal with these limitations, **secondary storage** like **magnetic disks** and **tapes** can be used to supplement memory, although they are slower.


# References


###### Information
- date: 2025.03.16
- time: 23:28