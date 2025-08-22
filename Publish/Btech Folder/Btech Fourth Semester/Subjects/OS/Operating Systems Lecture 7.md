---
Title: Operating Systems Lecture 6
Status: 
marker: 
tags: 
Date: 2025.01.23
Time: 11:05
---
Continued from [[Operating System Lecture 5]]

# Operating Systems Lecture 6

## **Process Control Block (PCB)**

The **Process Control Block (PCB)** is a critical data structure maintained by the operating system for each process. It contains all the information about a process, allowing the OS to manage and control it effectively. The PCB serves as a repository of key process attributes and facilitates context switching, process scheduling, and execution.

---

### **Structure of a PCB**

A typical PCB consists of the following fields:
1. **Process Identification Information:**
   - **Process ID (PID):** Unique identifier for the process.
   - **Parent Process ID (PPID):** ID of the process that spawned it.
   - **User ID and Group ID:** Identifies the user and group associated with the process.

2. **Process State:**
   - Represents the current state of the process:
     - **New:** Process is being created.
     - **Ready:** Process is ready to execute.
     - **Running:** Process is currently executing on the CPU.
     - **Waiting/Blocked:** Process is waiting for an I/O operation or event.
     - **Terminated:** Process has completed execution.

3. **Program Counter (PC):**
   - Stores the address of the next instruction to be executed for the process.

4. **CPU Registers:**
   - Contains the values of the CPU registers when the process is not executing.
   - Includes general-purpose registers, index registers, stack pointers, and flags.

5. **Memory Management Information:**
   - Includes details about the process's memory allocation:
     - **Base and Limit Registers:** Define the address space allocated to the process.
     - **Page Tables/Segment Tables:** Used in virtual memory systems.
     - **Memory Boundaries:** Information on the start and end addresses of the process's memory.

6. **Accounting Information:**
   - Tracks resource usage:
     - **CPU Usage:** Time the process has spent on the CPU.
     - **I/O Usage:** I/O operations performed by the process.
     - **Execution Time:** Total runtime of the process.
   - Used for billing and performance monitoring.

7. **I/O Status Information:**
   - List of I/O devices allocated to the process.
   - Status of I/O requests (e.g., pending, completed).

8. **Process Priority:**
   - Indicates the priority level of the process for scheduling purposes.

9. **Scheduling Information:**
   - Information used by the scheduler:
     - **Priority:** Determines the process's execution order.
     - **Queue Pointers:** Links to ready or waiting queues.
     - **Scheduling Policy:** Time-sharing, round-robin, etc.

10. **File Management Information:**
    - List of files opened by the process.
    - File descriptors and permissions.

![[IMG-20250730000528892.png|center|300]]

---

### **Role of PCB in Process Management**
1. **Process Tracking:**
   - The OS uses the PCB to track the status and details of every active process.

2. **Context Switching:**
   - During a context switch, the OS saves the current process's state in its PCB and loads the next process's state from its PCB.

3. **Scheduling:**
   - The scheduler uses PCB information (e.g., priority, state) to determine the next process to execute.

4. **Resource Allocation:**
   - The PCB ensures proper allocation and deallocation of resources like memory, I/O devices, and CPU time.
![[IMG-20250730000547451.png]]

---

### **PCB and Multitasking**

- In multitasking systems, the PCB allows the OS to maintain information for multiple processes simultaneously.
- Each process has its own PCB, which is stored in a **process table** managed by the OS.

---

### **Advantages of PCB**

1. **Efficient Process Management:**
   - Simplifies tracking and managing processes.
2. **Facilitates Multitasking:**
   - Enables the OS to switch between processes seamlessly.
3. **Resource Allocation:**
   - Ensures accurate and fair resource allocation for processes.

---
### **Challenges with PCB**
1. **Memory Overhead:**
   - Maintaining a PCB for each process consumes additional memory, especially in systems with a high number of processes.
2. **Complexity in Context Switching:**
   - Frequent context switching increases overhead due to constant saving and restoring of PCB data.

---
## Process Scheduling
There are queues that processes line up in to get their instructions executed.
- **Job Queues:** All Processes in the system.
- **Ready Queue:** Processes waiting to be executed in memory.
- **Device Queue:** Processes waiting for an I/O Signal
- Migration of process throughout the different queues is possible

## 

## References

###### Information
- Date: 2025.01.23
- Time: 11:05
- Continued from **Operating System Lecture 5**
- Continued to [[New Notes/Operating Systems Lecture 7]]

# References


###### Information
- date: 2025.01.23
- time: 11:05