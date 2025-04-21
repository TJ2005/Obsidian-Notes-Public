# Detailed Notes on Graphics Card Architecture and Performance

### Overview of Graphics Card Capabilities

Modern graphics cards perform **massive numbers of calculations** per second, especially when rendering complex, realistic graphics in video games. For example:
- **100 million calculations per second** are required to run *Mario 64* from 1996.
- **100 billion calculations per second** can run *Minecraft* from 2011.
- **36 trillion calculations per second** are needed to run high-end games like *Cyberpunk 2077* with realistic graphics.

This capability translates to a computation power so vast that if each human on Earth performed one calculation per second, we’d need **4,400 Earths** of people to match a modern graphics card’s speed.

[Reference Video](https://www.youtube.com/watch?v=h9Z4oGN89MU)

---

### Understanding GPU Architecture

To understand how graphics cards, or **GPUs (Graphics Processing Units)**, handle such immense computation, let’s dive into their structure and computational capabilities.

1. **Difference Between GPU and CPU**:
   - **CPU (Central Processing Unit)**: Has fewer cores (e.g., 24 cores), designed for flexibility and handling various tasks.
   - **GPU**: Has thousands of cores (e.g., over 10,000 CUDA cores), designed specifically to handle simple, repetitive calculations on vast amounts of data simultaneously.

#### CPU vs. GPU: The Airplane vs. Cargo Ship Analogy
   - **CPU (Jumbo Jet)**:
     - *Cargo Capacity*: Handles fewer calculations at a time but executes them at a high speed.
     - *Flexibility*: Can handle a variety of tasks, from running operating systems to interfacing with network and hardware devices.
     - *Example*: CPUs are efficient for tasks requiring quick evaluations of smaller datasets or complex tasks involving branching logic.

   - **GPU (Cargo Ship)**:
     - *Cargo Capacity*: Can perform massive numbers of calculations, albeit at a slower rate per individual task.
     - *Specialization*: Optimized for repetitive tasks that do not require complex logic, such as rendering video game graphics or running neural network calculations.
     - *Example*: Ideal for rendering graphics by processing massive datasets (e.g., pixel and texture information) in parallel.

#### Flexibility vs. Efficiency
   - **CPU**: Like airplanes, CPUs are flexible in their applications, handling everything from user applications to system-level tasks.
   - **GPU**: Like cargo ships, GPUs are specialized for moving massive amounts of data efficiently in specific contexts, such as matrix calculations and simple arithmetic operations.

---

### Components of the Graphics Card

The main components of a graphics card include:

1. **GPU Die (e.g., GA102 Chip)**:
   - The main chip, consisting of **28.3 billion transistors**, divided into hierarchical clusters and cores.
   - **Structure**:
     - **7 Graphics Processing Clusters (GPCs)**
     - Each GPC has **12 Streaming Multiprocessors (SMs)**
     - Each SM has **4 Warps**, **1 Ray Tracing Core**, **32 CUDA/Shading Cores**, and **1 Tensor Core**

2. **Types of Cores and Their Functions**:
   - **CUDA Cores**: Simple calculators used primarily for basic operations like addition and multiplication; optimized for video game graphics.
   - **Tensor Cores**: Specialized for matrix multiplication, essential for AI and neural networks.
   - **Ray Tracing Cores**: Fewer in number but larger in size; designed for executing ray-tracing algorithms, which provide realistic lighting and reflections.

3. **Fault Tolerance Through Binning**:
   - Not all GPUs are perfect; manufacturing defects may result in some cores or areas not functioning.
   - **Binning**: Defective areas are isolated and disabled. Chips with more functioning cores become high-end models (e.g., RTX 3090), while those with fewer active cores are sold as mid-range models (e.g., RTX 3080).

---

### Intricate Architecture of a CUDA Core

Each **CUDA Core** is like a simple calculator with basic functions such as addition and multiplication. Here’s how a single CUDA core operates:

- **410,000 transistors** in each core.
- Can perform **Fused Multiply and Add (FMA)** operations, the most common operation in graphics processing.
- 50,000 transistors within the core handle `A * B + C` calculations using 32-bit floating-point numbers.
- Each CUDA core completes one multiply and one add operation per clock cycle.

**Calculation Speed**:
- The **RTX 3090**, with 10,496 cores running at **1.7 GHz**, can perform **35.6 trillion calculations per second**.

---

### Additional Components on the GA102 Chip

1. **Memory Controllers**: Manage communication with graphics memory, such as GDDR6X SDRAM.
2. **Level 2 Cache**: A 6 MB SRAM cache that temporarily holds data for the GPU.
3. **Gigathread Engine**: Manages the scheduling of computations across clusters and streaming multiprocessors.

### Physical Structure of the Graphics Card

1. **Ports and Power Connectors**:
   - **Display Ports**: For connecting monitors.
   - **12V Power Connector**: Supplies power to the GPU.
   - **PCIe Interface**: Connects to the motherboard.

2. **Voltage Regulator Module (VRM)**:
   - Converts 12V input into 1.1V to supply high current to the GPU chip.

3. **Cooling System**:
   - Consists of heat sinks, heat pipes, and fans to manage the intense heat generated by high-power processing.

---

### Graphics Memory: GDDR6X and High Bandwidth Memory (HBM)

1. **GDDR6X SDRAM**:
   - **Capacity**: 24 GB in high-end models like the RTX 3090.
   - **Data Transfer**: Transfers data at 1.15 TB/s through a 384-bit bus width.
   - **PAM-4 Encoding**: Uses four voltage levels to represent two binary bits, achieving higher data transfer rates.
   
2. **High Bandwidth Memory (HBM)**:
   - Used in AI accelerators, not consumer GPUs.
   - **HBM3E**: Offers up to 36 GB per chip stack using Through Silicon Vias (TSVs) for high-speed, stacked memory.

---

### GPU Computational Architecture: SIMD and SIMT

1. **SIMD (Single Instruction Multiple Data)**:
   - Executes the same instruction across multiple data points simultaneously.
   - Used in rendering, where thousands of identical calculations are performed on vertices and pixels to create a 3D scene.
   - Example: Transforming each vertex’s X, Y, and Z coordinates in a 3D model.

2. **SIMT (Single Instruction Multiple Threads)**:
   - An enhancement over SIMD, allowing threads to execute at different rates.
   - Threads can diverge and converge based on data, making SIMT more flexible in handling complex, branching logic.
   
3. **Hierarchy of Execution Units**:
   - **Threads**: Single execution units mapped to CUDA cores.
   - **Warps**: Groups of 32 threads, executing the same instruction in lockstep.
   - **Thread Blocks**: Multiple warps assigned to a streaming multiprocessor.
   - **Grids**: Collections of thread blocks processed across the GPU.

---

### Parallel Processing in Graphics and Other Applications

1. **Video Game Rendering**:
   - Example of an **"embarrassingly parallel"** problem, where each calculation (e.g., transforming vertices, rendering pixels) can be performed independently.

2. **Bitcoin Mining**:
   - GPUs are used to generate SHA-256 hashes by running thousands of iterations on the same data but with different nonce values.
   - Though modern **ASICs** are much faster for mining, GPUs were originally popular due to their ability to perform massive parallel calculations.

3. **Tensor Cores for AI**:
   - Tensor cores are optimized for matrix multiplications, essential for AI and neural network operations.
   - **Matrix Multiplication Example**: Calculating values by multiplying rows and columns in matrices, with the tensor core executing multiple operations simultaneously.

---

### Conclusion

GPUs are highly specialized hardware that perform massive amounts of repetitive calculations on large datasets. While less flexible than CPUs, they excel in applications requiring parallel data processing, such as video game graphics, AI, and cryptographic hashing.

To learn more about GPU architecture, computational principles, and applications, check out the full video by Branch Education: [How Graphics Cards Work](https://www.youtube.com/watch?v=h9Z4oGN89MU). 