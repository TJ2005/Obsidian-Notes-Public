---
Title: Operating System Lecture 4
Status: 
marker:
  - "[[Operating Systems ( OS )]]"
tags: 
Date: 2025.01.11
Time: 12:06
---
Previous Lectures not present due to absence
# Operating System Lecture 4

## Purpose of Operating Systems

An operating system (OS) is designed to provide **ease of use** and **good performance** for the user. It serves as a **resource allocator**, managing system resources such as CPU time, memory, and storage, to ensure efficient use. 

For **mainframe** and **minicomputer** systems, the operating system must prioritize **user satisfaction** by providing a stable and responsive environment. The goal is to balance user needs with the efficient management of resources.

There is **no universally accepted definition** of an operating system, but generally, it can be described as a system that facilitates interaction between hardware and software, enabling programs to run smoothly.

The one program that is always running on the computer is the **kernel**. It forms the core of the operating system, managing hardware resources and providing basic services. 

Everything else, including system programs and application programs, operates on top of the kernel.

Additionally, **middleware** exists as a layer between the operating system and application programs, providing common services and facilitating communication between different software components.

Use NIST definitions to learn that.

## Features Required
Some essential features that an operating system must provide include:
- **Networking**: Enabling communication between different systems.
- **File System**: Efficient management of files and directories.
- **Security**: Protecting the system from unauthorized access and threats.
- **Protection**: Ensuring that processes and resources are protected from misuse or harm.
- **Reporting**: Generating logs or reports of system events and activities.
- **Logging**: Keeping a record of system events for debugging and analysis.
- **Windows Event Viewer**: A utility for viewing events and system logs in Windows-based operating systems.
# Generational Leaps in Software
![[IMG-20250730000528858.png]]

Generational leaps in software, particularly in the context of operating systems, have dramatically transformed how we interact with and manage computer systems. These advancements can be traced back to the early days of computing when machine language was the only way to communicate with hardware. Here's a brief overview of the significant stages:

### 1. **Machine Language (First Generation)**

In the early days, computers were programmed directly in machine language, consisting of binary code (0s and 1s) that the hardware could understand. This low-level code was extremely tedious to write and prone to errors. Each instruction directly controlled the CPU, leaving no room for abstraction or easy interaction with higher-level concepts like memory management or I/O handling. This era was characterized by hardware-centric programming, requiring deep knowledge of the machine’s architecture.

### 2. **Assembly Language (Second Generation)**

As the need for abstraction grew, assembly language emerged as a more manageable solution. Assembly uses symbolic representations of machine instructions, allowing programmers to write code that was more readable and less error-prone. However, it still required manual memory management and hardware-level optimizations. Early operating systems like UNIX were written in assembly, offering basic functionalities like process management and file handling. But programming in assembly remained complex and required intimate knowledge of the hardware.

### 3. **High-Level Programming Languages (Third Generation)**

With the advent of high-level programming languages like C and Fortran, developers could focus more on problem-solving and less on hardware-specific details. These languages introduced concepts like variables, functions, and structures, enabling the creation of more sophisticated programs. Operating systems like early versions of UNIX began to be written in C, which offered portability across different hardware architectures. This shift allowed for the creation of more complex, user-friendly operating systems and paved the way for multitasking and multiuser environments.

### 4. **Multitasking and Virtualization (Fourth Generation)**

As computing needs grew, the demand for multitasking (running multiple processes simultaneously) and better resource management led to the development of more advanced operating systems. Systems like Windows NT and Linux introduced the concept of virtual memory, allowing programs to use more memory than was physically available. Virtualization also allowed the creation of multiple isolated environments (virtual machines) on a single physical machine, enhancing resource utilization and system security. Operating systems began incorporating more complex kernel structures and the ability to manage multiple processes and users efficiently.

### 5. **Modern Operating Systems (Fifth Generation)**

The latest generation of operating systems is defined by advanced capabilities, such as real-time processing, cloud integration, and AI-powered automation. Operating systems like modern Linux distributions, macOS, and Windows 10+ are optimized for modern hardware, offer graphical user interfaces (GUIs), and support a wide range of hardware architectures. Features like containerization (Docker) and orchestration (Kubernetes) allow developers to deploy scalable applications with greater ease. Furthermore, security is a top priority, with systems incorporating multi-layered defenses, encryption, and sandboxing technologies.

### Summary of the Evolution:

- **First Generation (Machine Language):** Direct binary code for hardware control.
- **Second Generation (Assembly Language):** Symbolic instructions for easier programming but still hardware-dependent.
- **Third Generation (High-Level Languages):** Portability and abstraction, enabling more complex and sophisticated OS designs.
- **Fourth Generation (Multitasking & Virtualization):** Advanced memory management, multi-user systems, and virtualization.
- **Fifth Generation (Modern OS with Cloud and AI):** Highly sophisticated, secure, and optimized for modern hardware, supporting cloud computing and AI.

Each leap in this evolutionary journey has made computing more accessible, efficient, and powerful, allowing us to run complex applications, manage vast amounts of data, and even simulate entire environments within a single computer. Operating systems today serve as the backbone of all digital interactions, making it possible for users to seamlessly interact with technology.


# Operations
- I/O Devices and the CPU can execute concurrently
- Each Device controller is in charge of a particular device type
- Each Device has a local buffer
- Each Device controller type has an operating system device driver to manage it
- CPU Moves data from / to main memory to/from local buffers
- I/O is from the device to the local buffer of the controllers
- Device Controller informs that it has finished its operation by causing an interrupt


## Common Functions of Interrupt
- Interrupt Transfers control to the interrupt service routine through the interrupt service routine.



## References
- Continued to [[Operating System Lecture 4]]
###### Information
- date: 2025.01.11
- time: 12:06
