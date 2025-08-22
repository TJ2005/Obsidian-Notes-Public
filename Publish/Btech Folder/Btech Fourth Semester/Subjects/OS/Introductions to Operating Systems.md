---
Title: Introductions to Operating Systems
Status: 
marker:
  - "[[operating system]]"
tags: 
Date: 2025.01.23
Time: 11:21
---
This note is generated and a summarized version of the introduction.
# Operating System Concepts - Notes

## Overview
A **Computer** can be divided into four components
- Hardware
	- CPU I/O
- **Operating Systems**
- Application programs
- Users

## What's an Operating system
An **Operating System (OS)** is software that manages computer hardware and provides services for application programs. It acts as an intermediary between users and the hardware. 

Definition(s): The software "master control application" that runs the computer. It is the first program loaded when the computer is turned on, and its main component, the [[kernel]], resides in [[memory]] at all times. The operating system sets the standards for all application programs (such as the Web server) that run in the computer. The applications communicate with the operating system for most user interface and file management operations.

- Users wants:
	- ease of use
	- good performance
	- resource utilization

“The program running at all times on the computer” is the **[[kernel]]**, part of the operating system.
### Key Functions of an OS:
- Process Management
- Memory Management
- Storage Management
- Protection and Security
- User Interface

### Types of Operating Systems:
1. **Batch OS** – Executes jobs in batches without user interaction.
2. **Time-sharing OS** – Allows multiple users to use the system simultaneously.
3. **Distributed OS** – Manages multiple computers as a single system.
4. **Real-time OS (RTOS)** – Provides real-time task execution for critical applications.
5. **Mobile OS** – Designed for mobile devices (e.g., iOS, Android).

### OS Components:
- **Kernel** – Core part that manages hardware and system resources.
- **Shell** – Interface for user interaction.
- **File System** – Organizes and stores data.
- **Device Drivers** – Interfaces between hardware and the OS.
- **System Utilities** – Tools for system maintenance and optimization.

---

## Process Management
A **process** is a program in execution. The OS is responsible for scheduling and managing processes efficiently.

### Key Concepts:
- **Process States:** New, Ready, Running, Waiting, Terminated.
- **Process Scheduling:** Allocates CPU time to processes.
- **Interprocess Communication (IPC):** Enables communication between processes.
- **Threads:** Lightweight processes that share resources within a process.
- **Deadlock Handling:** Prevents or resolves resource conflicts.

---

## Memory Management
Memory management ensures efficient utilization of system memory.

### Key Concepts:
- **Swapping:** Moving processes between main memory and disk.
- **Paging:** Dividing memory into fixed-size blocks.
- **Segmentation:** Dividing memory into variable-sized segments.
- **Virtual Memory:** Extends RAM using disk space.

---

## Storage Management
The OS manages storage devices and file systems.

### Key Concepts:
- **File System Structure:** Organizes files in directories.
- **Disk Scheduling Algorithms:** Optimize read/write operations.
- **RAID (Redundant Array of Independent Disks):** Improves performance and reliability.

---

## Protection and Security
The OS enforces security policies to protect data and resources.

### Key Concepts:
- **Access Control:** Restricts user permissions.
- **Encryption:** Secures data transmission.
- **Authentication Methods:** Passwords, biometrics, tokens.
- **Firewalls and Intrusion Detection Systems (IDS):** Protect against attacks.

---

## Advanced Topics
- **Virtual Machines:** Run multiple OS instances on a single machine.
- **Distributed Systems:** Enable resource sharing over networks.
- **Cloud Computing:** Provides scalable, on-demand computing resources.
- **Mobile OS Considerations:** Power efficiency, app sandboxing.

---

## Case Studies
- **Linux:** Open-source, widely used in servers.
- **Windows:** User-friendly, dominant in desktops.
- **Mac OS:** Unix-based, optimized for Apple devices.
- **Android & iOS:** Leading mobile operating systems.

---

# Types of Operating Systems

- **Single User:** One user at a time (e.g., MS-DOS).
- **Multi-user:** Multiple users access resources simultaneously (e.g., UNIX).
- **Multitasking:** Runs several programs concurrently (e.g., Windows, Linux).
- **Interactive:** Immediate user interaction and response (e.g., modern desktops).
- **Real-Time:** Responds to events within strict time limits or else the system crashes! (e.g., VxWorks).
- **Batch Processing:** Executes jobs in batches with minimal user input (e.g., early mainframes in banking for batch payment of salaries!).
- **Distributed:** Manages multiple networked computers as one system (e.g., Amoeba).
# Operating System Services: Comprehensive Summary

## **1. User Interface**
- **Types**:  
  - **CLI** (Command-Line Interface)  
  - **GUI** (Graphical User Interface)  
  - **Batch Interface** (Script-based execution)[1][4].

---

## **2. Program Execution**
- **Process Management**:  
  - Loads programs into memory and executes them.  
  - Handles **process creation/deletion**, suspension/resumption.  
  - Manages **synchronization**, **inter-process communication**, and **deadlock handling**[1][3][4].  
- **Tools**: Provides editors/debuggers for program creation[3].

---

## **3. I/O Operations**
- Manages device drivers to abstract hardware specifics.  
- Facilitates **DMA (Direct Memory Access)** for efficient data transfer[1][5].  

---

## **4. File System Management**
- Creates, modifies, and deletes files.  
- Manages permissions and directory structures[1][4].

---

## **5. Communication**
- **Inter-Process**: Shared memory or message passing.  
- **Network**: Enables data exchange between distributed systems[1][4].

---

## **6. Error Detection & Safety**
- Detects hardware errors (e.g., power failure, low printer paper).  
- Handles software exceptions and security breaches (CIA triad: **Confidentiality, Integrity, Availability**)[1][3][5].

---

## **7. Resource Allocation**
- **CPU Scheduling**: Prioritizes processes (e.g., Round Robin).  
- **Memory Management**: Allocates/deallocates RAM.  
- **I/O Device Management**: Assigns devices to processes[1][3][4].

---

## **8. Accounting**
- Tracks resource usage (CPU time, memory) for billing and statistics[3][4].

---

## **9. Protection & Security**
- Isolates processes to prevent interference.  
- Implements **authentication**, **access control**, and **encryption**[3][5].

---

## **10. Command Interpretation**
- Translates user commands (CLI) into system actions via shells[3][4].

---

## **11. Resource Management**
- Optimizes utilization of CPU, memory, and I/O devices[3][4].

---

### **Key Implementation Mechanisms**
- **Kernel**: Enforces security via user/kernel modes and manages hardware[5].  
- **System Calls**: Bridge user programs and OS services (e.g., `read()`, `write()`)[4][5].  
- **Context Switching**: Facilitates multitasking via PCB (Process Control Block)[4][5].


# References


###### Information
- date: 2025.01.23
- time: 11:21