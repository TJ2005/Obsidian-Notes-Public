---
Title: "Operating System Lecture 11"
Status: 
marker: 
tags: 
Date: "2025.02.20"
Time: "09:57"
---
# Critical Section and Readers-Writers Problem in Operating Systems

When studying operating systems, especially for exams or implementation, understanding how to manage concurrent access to shared resources is crucial. This involves dealing with **critical sections** and solving synchronization problems like the **Readers-Writers Problem**. Here's a straightforward guide to help you grasp these concepts:

## Critical Section

A **critical section** is a part of a program where shared resources (like variables, memory, or files) are accessed. To ensure data consistency and avoid race conditions, only one process should execute in its critical section at a time.

### Key Concepts

- **Mutual Exclusion**: Ensures only one process is in the critical section at any time.
- **Progress**: If no process is in the critical section, other processes should decide who enters next.
- **Bounded Waiting**: Limits the number of times other processes can enter before a waiting process gets a chance.

### Solution Approaches

- **Peterson’s Algorithm**: A software-based solution for two processes.
- **Mutex Locks**: Binary locks that provide mutual exclusion.
- **Semaphores**: Synchronization variables that control access to the critical section.

### Pseudo Code for Mutual Exclusion (Using a Lock Variable)

```c
int lock = 0;  // 0 = unlocked, 1 = locked

void process() {
    while (true) {
        // Entry Section
        while (lock == 1);  // Busy-waiting until lock is released
        lock = 1;  // Acquire the lock

        // Critical Section
        // (Access shared resource)

        // Exit Section
        lock = 0;  // Release the lock

        // Remainder Section (Non-critical work)
    }
}
```

### Pseudo Code Using Semaphores (More Efficient)

```c
semaphore mutex = 1; // Binary semaphore (1 = available)

void process() {
    while (true) {
        wait(mutex);  // Acquire lock

        // Critical Section
        // (Access shared resource)

        signal(mutex); // Release lock

        // Remainder Section
    }
}
```

## Readers-Writers Problem

The **Readers-Writers Problem** is a classic synchronization issue that deals with managing access to a shared resource (e.g., a file or database) where:
- **Readers** can read simultaneously.
- **Writers** need exclusive access.

### Types of Readers-Writers Problem

1. **First Readers-Writers Problem (Readers Priority)**
   - Multiple readers can read simultaneously.
   - A writer must wait until all readers finish.

2. **Second Readers-Writers Problem (Writers Priority)**
   - If a writer is waiting, new readers cannot start reading.
   - Gives priority to writers to avoid starvation.

### Pseudo Code for Readers-Writers using Semaphores

#### Solution with Readers Priority

```c
semaphore mutex = 1;      // Controls access to read_count
semaphore rw_mutex = 1;   // Controls access to the shared resource
int read_count = 0;       // Number of active readers

void reader() {
    while (true) {
        wait(mutex);       // Lock to update read_count
        read_count++;
        if (read_count == 1) wait(rw_mutex); // First reader blocks writers
        signal(mutex);     // Unlock read_count

        // Critical Section (Reading the resource)

        wait(mutex);
        read_count--;
        if (read_count == 0) signal(rw_mutex); // Last reader unlocks resource
        signal(mutex);

        // Remainder Section
    }
}

void writer() {
    while (true) {
        wait(rw_mutex); // Exclusive access to resource

        // Critical Section (Writing the resource)

        signal(rw_mutex); // Release lock

        // Remainder Section
    }
}
```

#### Solution with Writers Priority

```c
semaphore mutex = 1;
semaphore rw_mutex = 1;
semaphore queue = 1;      // Ensures writers get priority
int read_count = 0;

void reader() {
    while (true) {
        wait(queue);     // Ensure writers get priority
        wait(mutex);
        read_count++;
        if (read_count == 1) wait(rw_mutex);
        signal(mutex);
        signal(queue);

        // Critical Section (Reading)

        wait(mutex);
        read_count--;
        if (read_count == 0) signal(rw_mutex);
        signal(mutex);

        // Remainder Section
    }
}

void writer() {
    while (true) {
        wait(queue);  // Ensures no reader or writer enters
        wait(rw_mutex);

        // Critical Section (Writing)

        signal(rw_mutex);
        signal(queue);

        // Remainder Section
    }
}
```

### Case Discussion

- **Readers Priority**: Useful when read operations are more frequent and should not be delayed by writers.
- **Writers Priority**: Prevents writer starvation by ensuring writers get access when they are waiting, which is useful when write operations are critical.

Understanding these concepts and their implementations will help you tackle exam questions and implement synchronization mechanisms effectively.



# References


###### Information
- date: 2025.02.20
- time: 09:57