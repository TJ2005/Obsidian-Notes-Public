---
Title: "Operations on Process"
Status: 
marker: 
tags: 
Date: "2025.05.11"
Time: "21:25"
---
Process creation and termination are fundamental operations in operating systems, enabling dynamic execution and resource management. Here's a concise technical overview:

## Process Creation
**fork() system call** creates child processes by duplicating the parent's address space, code, and resources[1][5][11]. Key characteristics:
- Returns child's PID to parent, 0 to child, -1 on error[2][12]
- Creates identical copies of parent's memory space[2][11]
- Parent/child execute independently after fork()[11]

**exec() family** replaces process memory with new program:
- Overwrites code/text, data, heap, and stack segments[3][6]
- Preserves PID and open file descriptors by default[3]
- Typically used after fork() to run new programs[3][11]

**Windows alternative**: CreateProcess() combines fork+exec functionality[7]:
```c
CreateProcess(NULL, command, ..., &si, &pi);
```

## Process Termination
**exit()** system call:
- Releases resources (memory, files, I/O buffers)[10][14]
- Returns status to parent via wait()[10][14]
- OS deallocates resources and removes PID[10][14]

**wait()/waitpid()** synchronization:
```c
pid_t pid = wait(&status);  // Blocks until child exits[4][14]
```
- Retrieves child exit status and reaps zombies[4][8]
- Mandatory to prevent zombie processes[8][15]

**Termination scenarios**:
1. **Normal exit** via return/exit()[10]
2. **Abort** by parent via abort() system call[10][14]
3. **Cascading termination** when parent dies[10][14]
4. Resource overflows/I/O failures[10]

## Zombie vs Orphan Processes
|                | Zombie Process                          | Orphan Process                       |
|----------------|-----------------------------------------|--------------------------------------|
| **State**      | Terminated but not reaped               | Active with dead parent              |
| **Creation**   | Parent fails to call wait()             | Parent exits before child completion |
| **Resolution** | Parent must call wait()                 | Reparented to init (PID 1)[9][13]    |
| **Risk**       | Process table leakage[15]               | Automatic handling by OS[9][13]      |

**Zombie identification**: 'Z' in ps STAT column[8]

## Code Examples
**UNIX workflow**:
```c
pid_t pid = fork();
if (pid == 0) {  // Child
    execl("/bin/ls", "ls", NULL); 
    exit(255);  // Fallback if exec fails
} else {         // Parent
    wait(NULL); 
    printf("Child completed\n");
}
```

**Windows workflow**:
```c
CreateProcess("C:\\WINDOWS\\system32\\calc.exe", ..., &pi);
WaitForSingleObject(pi.hProcess, INFINITE);
CloseHandle(pi.hProcess);
```

Key implementation details:
- fork() preserves open files and execution context[11][12]
- exec() maintains PID but replaces memory mapping[3][6]
- wait() is essential for proper process cleanup[4][8]
- Windows handles process creation atomically[7]
