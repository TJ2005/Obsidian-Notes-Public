---
Title: GPU Working
Status: 
marker: 
tags: 
Date: 2024.12.10
Time: 21:48
---
# Understanding Graphics Processing Units (GPUs)

In this note, we will explore the architecture and functionality of Graphics Processing Units (GPUs), their comparison with Central Processing Units (CPUs), and their applications in various fields such as video gaming, AI, and cryptocurrency mining.

## 1. Introduction to GPU Performance

The performance of a GPU is often measured in terms of calculations per second. For instance:

- **Mario 64 (1996)**: Requires approximately $100 \text{ million calculations/second}$.
- **Minecraft (2011)**: Requires around $100 \text{ billion calculations/second}$.
- **Cyberpunk 2077**: Requires about $36 \text{ trillion calculations/second}$.

To conceptualize $36 \text{ trillion calculations/second}$, consider that if every person on Earth performed one calculation per second, we would need about $4,400$ Earths to match the computational power of a modern GPU.

## 2. GPU vs. CPU

### 2.1 Core Count

- **GPU**: Over $10,000$ cores.
- **CPU**: Typically around $24$ cores.

### 2.2 Analogy

- **GPU**: Like a massive cargo ship, capable of handling a large volume of calculations but at a slower rate.
- **CPU**: Like a jumbo jet, capable of performing fewer calculations quickly and flexibly.

### 2.3 Flexibility

- **CPUs**: Can run a variety of programs and instructions.
- **GPUs**: Limited to simple arithmetic operations and cannot run operating systems or interface with input devices.

## 3. GPU Architecture

### 3.1 Physical Components

- **Printed Circuit Board (PCB)**: Houses all components.
- **Graphics Processing Unit (GPU)**: Central chip (e.g., GA102) with $28.3 \text{ billion transistors}$.
- **Cores**:
    - $10,752$ CUDA cores
    - $336$ Tensor cores
    - $84$ Ray tracing cores

### 3.2 CUDA Cores

CUDA cores perform basic arithmetic operations. The most common operation is the **Fused Multiply-Add (FMA)**, represented as:

$$ \text{FMA}(A, B, C) = A \times B + C $$

### 3.3 Memory Architecture

- **Graphics Memory**: GDDR6X SDRAM with $24 \text{ GB}$ capacity.
- **Bandwidth**: Approximately $1.15 \text{ TB/s}$.

### 3.4 Data Transfer

The GPU's memory architecture allows for high-speed data transfer, utilizing multiple voltage levels for efficient communication.

## 4. Computational Architecture

### 4.1 SIMD and SIMT

- **Single Instruction Multiple Data (SIMD)**: Executes the same instruction across multiple data points.
- **Single Instruction Multiple Threads (SIMT)**: Allows threads to progress at different rates, improving flexibility.

### 4.2 Thread Management

Threads are organized into warps (groups of $32$) and managed by the Gigathread Engine, which schedules computations across the GPU.

## 5. Applications of GPUs

### 5.1 Video Game Rendering

GPUs excel in rendering graphics due to their ability to handle embarrassingly parallel tasks. For example, transforming vertices from model space to world space can be expressed as:

### 5.2 Cryptocurrency Mining

GPUs were initially used for Bitcoin mining due to their ability to perform numerous iterations of the SHA-256 hashing algorithm. The performance can be quantified as:

$$ \text{Hashes/Second} = 95 \text{ million} $$

### 5.3 Neural Networks

Tensor cores are specifically designed for matrix operations, performing calculations such as:

$$ \text{Output} = A \times B + C $$

where $A$, $B$, and $C$ are matrices.

## 6. Conclusion

GPUs represent a significant advancement in computational technology, enabling high-performance tasks in gaming, AI, and data processing. Their architecture is specifically designed to handle massive parallel computations efficiently.

## 7. Refe