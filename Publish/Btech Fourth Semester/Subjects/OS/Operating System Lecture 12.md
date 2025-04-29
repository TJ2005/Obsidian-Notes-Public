---
Title: Operating System Lecture 9
Status: 
marker: 
tags: 
Date: 2025.01.30
Time: 09:04
---
Continued from [[Operating Systems Lecture 6]]
# Process Creation

- Parent process create children processes, which, in turn create other processes, forming a tree of processes
- Generally, process identified and managed via a process identifier (pid)
- Resource sharing options
  - Parent and children share all resources
  - Children share subset of parent's resources
  - Parent and child share no resources
- Execution options
  - Parent and children execute concurrently
  - Parent waits until children terminate
- Address space
  - Child duplicate of parent
  - Child has a program loaded into it
- UNIX examples The fork() System Call:
  - The fork() system call is used to create a new process, which is a child process.
    - The child process is an exact copy of the parent process, including its memory space, code, and resources.
    - After fork(), both the parent and child processes start executing independently from the same point in the code.
- The exec() System Call:
  - After a fork(), the child process can use the exec() system call to replace its current code and memory space with a completely new program.
    - This means the child process stops executing its original program and starts running the new program specified in the exec() call.
  - What Happens Internally:
    - The memory space of the calling process (in this case, the child process) is completely replaced by the new program.
    - This includes replacing the code, stack, heap, and data segments of the current process with those of the new program.
    - However, the process ID (PID) of the child process remains the same.
  - Parent process calls wait() waiting for the child to terminate

# Process Termination

- Process executes last statement and then asks the operating system to delete it using the exit() system call.
  - Returns status data from child to parent (via wait())
  - Process' resources are deallocated by operating system
- Parent may terminate the execution of children processes using the abort() system call. Some reasons for doing so:
  - Child has exceeded allocated resources
  - Task assigned to child is no longer required
  - The parent is exiting and the operating systems does not allow a child to continue if its parent terminates
- Some operating systems do not allow child to exist if its parent has terminated. If a process terminates, then all its children must also be terminated.
  - Cascading termination. All children, grandchildren, etc. are terminated.
  - The termination is initiated by the operating system.
- The parent process may wait for termination of a child process by using the wait() system call. The call returns status information and the pid of the terminated process.
  - pid = wait(&status)
- If no parent waiting (did not invoke wait()) process is a zombie
- If parent terminated without invoking wait(), process is an orphan

*(Source: Dhruv Rathod)*



# References

###### Information

- date: 2025.01.30
- time: 09:04