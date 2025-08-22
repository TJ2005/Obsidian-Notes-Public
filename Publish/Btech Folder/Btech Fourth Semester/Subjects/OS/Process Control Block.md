---
Title: Process Control Block
Status: 
marker: 
tags: 
Date: 2025.05.11
Time: 20:43
---

## Process Control Block

Each process is represented in the Linux kernel by a `task_struct` structure, which contains all essential information about the process[2][4]:

- **pid**: Unique process identifier.
- **state**: Current process state (as above).
- **program counter**: Address of the next instruction to execute.
- **CPU registers**: Contents of all processor-specific registers for this process.
- **CPU scheduling info**: Priority, time slice, and pointers for scheduling queues.
- **Memory management info**: Memory regions (code, data, stack, heap) allocated to the process.
- **Accounting info**: CPU time used, elapsed time since start, time limits.
- **I/O status info**: Allocated I/O devices and a list of open files.

![[IMG-20250730000528915.png|center]]


A process in an operating system transitions through several states during its lifecycle. The state reflects the current activity or condition of the process. Key process states in Linux, as tracked by the `state` field in `task_struct`, include:

- **TASK_RUNNING**: The process is either currently executing on the CPU or is ready and waiting in a run queue to be scheduled[3][5].
- **TASK_INTERRUPTIBLE**: The process is sleeping, waiting for a specific event or condition (such as I/O completion). It can be awakened by signals or events[3][5].
- **TASK_UNINTERRUPTIBLE**: Similar to TASK_INTERRUPTIBLE, but the process cannot be awakened by signals. Used for critical operations that must not be interrupted[3][5].
- **__TASK_STOPPED**: The process has been stopped, usually by receiving a stop signal or for debugging[5].
- **__TASK_TRACED**: The process is being traced (e.g., by a debugger)[5].
- **TASK_DEAD / EXIT_ZOMBIE**: The process has finished execution but still has an entry in the process table (zombie state)[3].

These states are represented as flags (bitfields) in the `state` field[1][3][5].

---

## Example: task_struct Fields

```c
struct task_struct {
    pid_t t_pid;                  // Process identifier
    long state;                   // Process state (e.g., TASK_RUNNING)
    unsigned int time_slice;      // Scheduling information
    struct task_struct *parent;   // Pointer to parent process
    struct list_head children;    // List of child processes
    struct files_struct *files;   // List of open files
    struct mm_struct *mm;         // Memory management info
    // ... (other fields omitted)
};
```
![[IMG-20250730000547832.png]]

---

## Summary

- **Process state** is a key attribute, indicating whether a process is running, waiting, stopped, or terminated.
- The **task_struct** structure in the Linux kernel encapsulates all information about a process, including its state, scheduling, memory, and I/O resources.
- State transitions and process management are handled by the kernel, which updates the `state` field and related fields as processes execute, wait, or terminate[2][3][5].

# References


###### Information
- date: 2025.05.11
- time: 20:43