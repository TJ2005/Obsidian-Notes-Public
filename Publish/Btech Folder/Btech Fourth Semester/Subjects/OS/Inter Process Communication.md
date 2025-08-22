---
Title: "Inter Process Communication"
Status: 
marker: 
tags: 
Date: "2025.05.11"
Time: "21:42"
---
Inter-Process Communication (IPC) enables processes to collaborate through **shared memory** or **message passing**, each with distinct advantages and implementation challenges. Here's a technical breakdown:

![[IMG-20250730000528804.png]]
## Shared Memory Model
- **Mechanism**: Establishes a common memory region accessible by multiple processes[1][4].  
- **Performance**:  
  - **Direct memory access** eliminates repeated system calls after initial setup[5][6]  
  - Ideal for **high-throughput data exchange** (e.g., GPU rendering pipelines)[3]  
- **Implementation**:  
  ```c
  // UNIX example
  int shm_id = shmget(key, size, IPC_CREAT | 0666);
  char *shmem = shmat(shm_id, NULL, 0);
  ```
- **Challenges**:  
  - Requires explicit **synchronization** (semaphores/mutexes) to prevent race conditions[4]  
  - Complex debugging due to concurrent memory access[5]  

## Message Passing Model
- **Mechanism**: Exchanges structured messages via `send()`/`receive()` system calls[2][4]  
- **Performance**:  
  - **Slower** due to kernel involvement per message[5][6]  
  - Better for **small data payloads** and distributed systems[1][4]  
- **Implementation**:  
  ```c
  // MPI example
  MPI_Send(buffer, count, datatype, dest, tag, comm);
  MPI_Recv(buffer, count, datatype, source, tag, comm, &status);
  ```
- **Advantages**:  
  - Built-in **synchronization** via blocking operations[2]  
  - Naturally supports **networked communication**[4]  

## Key Comparison
| Aspect                | Shared Memory                          | Message Passing                      |
|-----------------------|----------------------------------------|--------------------------------------|
| **Speed**             | Memory-speed access (~ns latency)[5][6] | System call overhead (~µs latency)[6] |
| **Data Size**         | Optimal for large datasets[3][5]       | Best for small messages[1][4]        |
| **Synchronization**   | Manual (semaphores)[4]                 | Automatic (blocking sends)[2]        |
| **Complexity**        | Higher programmer effort[1][5]         | Simplified API usage[2][4]           |
| **Use Case**          | Single-machine multithreading[4][5]    | Distributed systems/clusters[4][6]   |

## Hybrid Approach
Modern systems combine both models for optimal performance[3]:
1. **Message passing** initiates communication and synchronizes processes  
2. **Shared memory** handles bulk data transfer  
Example:  
```c
// QNX-style graphics pipeline
msg.shmem_handle = create_shared_buffer();  // Shared memory setup
send(server, &msg);                          // Message with metadata
wait_reply();                                // Synchronization point
```
This achieves **nanosecond data access** with **microsecond-level coordination**[3][5].

## Design Considerations
- **Latency vs Throughput**: Shared memory reduces latency for frequent access, while message passing simplifies occasional transfers[5][6]  
- **Error Handling**: Message passing naturally isolates process failures; shared memory requires crash recovery mechanisms[4]  
- **Security**: Message passing allows encryption; shared memory relies on process privileges[1]  

Choose shared memory for **real-time processing** on shared hardware, and message passing for **modular distributed systems**. Hybrid implementations address scenarios requiring both high bandwidth and synchronization[3][5].

Shared memory enables high-performance inter-process communication (IPC) by allowing multiple processes to access a common memory region. This approach requires explicit synchronization management by developers rather than the operating system. Here's a technical breakdown:

## Shared Memory Implementation
**Establishing Communication Links**
1. **Memory Allocation**  
   - UNIX: `shmget()` creates shared segment, `shmat()` attaches to process space  
   ```c
   key_t key = ftok("shmfile",65);
   int shmid = shmget(key,1024,0666|IPC_CREAT);
   char *str = (char*) shmat(shmid,(void*)0,0);  // Attach [5]
   ```
   - Windows: `CreateFileMapping()` with system paging file  
   ```c
   HANDLE hMapFile = CreateFileMapping(INVALID_HANDLE_VALUE, NULL, PAGE_READWRITE, 0, BUF_SIZE, "Global\\MyFileMappingObject"); [1]

2. **Link Characteristics**
   - **Capacity**: Fixed at creation (e.g., 1024 bytes in example)
   - **Directionality**: Bidirectional by default
   - **Participants**: Multiple processes via `shmget()`/`OpenFileMapping()`

**Synchronization Mechanisms**  
Developers must implement:
- **Semaphores**:  
  ```
  sem_wait(&sem);  // Atomic decrement
  /* Critical section */
  sem_post(&sem);  // Increment[4]
  ```
- **Mutexes**:  
  ```
  pthread_mutex_lock(&shared_mutex);
  /* Memory access */
  pthread_mutex_unlock(&shared_mutex);
  ```

## Key Implementation Considerations

| Aspect               | Shared Memory Solution                          |
|----------------------|-------------------------------------------------|
| **Link Association** | Multiple processes via same key/name           |
| **Message Size**     | Variable - limited by allocated memory size    |
| **Buffering**        | Unbounded (manual management)                  |
| **Blocking**         | Non-blocking access with manual synchronization|

**Performance Characteristics**
- Latency: 50-100 ns for local access [4]
- Throughput: Up to 10GB/s on modern hardware
- Overhead: Single system call during setup vs per-operation in message passing

## Code Example: Producer-Consumer Pattern
```
// Producer process
sem_wait(&empty);        // Wait for empty slot
sem_wait(&mutex);        // Enter critical section
sprintf(shmem_ptr, data); 
sem_post(&mutex);  
sem_post(&full);         // Signal data availability

// Consumer process
sem_wait(&full);  
sem_wait(&mutex);
process_data(shmem_ptr);  
sem_post(&mutex);
sem_post(&empty);
```

## Challenges and Solutions
1. **Race Conditions**  
   - Use atomic operations or hardware-supported locks
2. **Stale Data**  
   - Implement versioning counters in shared memory
3. **Security**  
   - Set ACLs via `shmctl(..., IPC_SET, ...)` in UNIX [5]
   - Use `SECURITY_ATTRIBUTES` in Windows [1]

**Optimization Technique**  
```
madvise(shmem_ptr, size, MADV_SEQUENTIAL);  // Linux prefetch hint
FlushViewOfFile(shmem_ptr, size);           // Windows write commit[1]
```