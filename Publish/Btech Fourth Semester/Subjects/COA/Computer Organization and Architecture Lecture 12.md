---
Title: "Computer Organization and Architecture Lecture 12"
Status: 
marker: 
tags: 
Date: "2025.02.13"
Time: "08:39"
---
### **Computer Organization and Architecture - Lecture 12**

#### **Characteristics of Memory**

In computer architecture, memory is characterized by the following factors:

1. **Memory Speed**: Refers to the time it takes to access data from memory. Faster memory is crucial for improving system performance.
2. **Memory Storage Capacity**: The amount of data that can be stored in the memory.

When developers aim to improve one parameter, often another parameter may degrade. This creates a trade-off between memory speed and capacity, for example.

---

#### **The Memory Pyramid**

The memory hierarchy is designed to offer a balance between memory speed and storage capacity. Different types of memory have different speeds and capacities. The general hierarchy includes:

- **Registers (1 cycle)**: The fastest form of memory, located inside the CPU. It provides immediate access to data and instructions.
- **Cache (10 cycles)**: A smaller but faster form of memory, located close to the CPU, that stores frequently accessed data for quick retrieval.
- **Main Memory (~100 cycles)**: Also known as RAM, stores data that is currently being used by the computer.

Below is a visual representation of the memory hierarchy:

<center> <img width=400px src="https://www.cs.swarthmore.edu/~kwebb/cs31/f18/memhierarchy/figures/MemoryHierarchy.png"></img> 

---

#### **Capacitor and Power Supply**

A capacitor in memory technology cannot hold a charge indefinitely. That's why for many types of memory, especially volatile ones, there must either be a continuous power supply or methods to refresh the memory.

---

#### **Wait Cycles**

In some cases, memory access takes more time, requiring **wait cycles**. These are cycles during which the CPU must wait before accessing data from slower memory, resulting in delays in processing.

---
Continued to [[Computer Organization and Architecture Lecture 13]]