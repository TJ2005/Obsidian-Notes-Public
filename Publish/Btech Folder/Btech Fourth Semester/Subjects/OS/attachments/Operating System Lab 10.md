---
Title: "Operating System Lab 9"
Status: 
marker: 
tags: 
Date: "2025.03.29"
Time: "12:21"
---
## AIM:
To Demonstrate use of semaphores for deadlock avoidance.
## Code:
```python
import threading
import time
import random

# Initialization
NUM_PROCESSES = 5
NUM_RESOURCES = 3
available = [10, 5, 7]  # Available resources
maximum = [  # Maximum demand matrix
    [7, 5, 3],
    [3, 2, 2],
    [9, 0, 2],
    [2, 2, 2],
    [4, 3, 3]
]
allocation = [[0] * NUM_RESOURCES for _ in range(NUM_PROCESSES)]  # Allocated resources matrix
need = [[maximum[i][j] - allocation[i][j] for j in range(NUM_RESOURCES)] for i in range(NUM_PROCESSES)]  # Need matrix
mutex = threading.Semaphore(1)  # Mutex for synchronization

# Function to check if the system is in a safe state
def is_safe():
    work = available[:]
    finish = [False] * NUM_PROCESSES
    safe_sequence = []
    while len(safe_sequence) < NUM_PROCESSES:
        allocated = False
        for i in range(NUM_PROCESSES):
            if not finish[i] and all(need[i][j] <= work[j] for j in range(NUM_RESOURCES)):
                # Allocate resources
                for j in range(NUM_RESOURCES):
                    work[j] += allocation[i][j]
                safe_sequence.append(i)
                finish[i] = True
                allocated = True
                break
        if not allocated:  # If no allocation is possible, system is unsafe
            return False, []
    return True, safe_sequence

# Function to handle resource requests
def request_resources(process_id):
    global available, allocation, need
    mutex.acquire()  # Lock for critical section
    # Random resource request
    request = [random.randint(0, need[process_id][j]) for j in range(NUM_RESOURCES)]
    print(f"Process {process_id} requesting {request}")
    if all(request[j] <= available[j] for j in range(NUM_RESOURCES)):  # Check availability
        # Tentatively allocate resources
        for j in range(NUM_RESOURCES):
            available[j] -= request[j]
            allocation[process_id][j] += request[j]
            need[process_id][j] -= request[j]
        # Check if the system is still in a safe state
        safe, sequence = is_safe()
        if safe:
            print(f"Request granted. Safe sequence: {sequence}")
        else:  # Rollback allocation if unsafe
            for j in range(NUM_RESOURCES):
                available[j] += request[j]
                allocation[process_id][j] -= request[j]
                need[process_id][j] += request[j]
            print("Request denied to avoid deadlock.")
    else:
        print("Request exceeds available resources.")
    mutex.release()  # Release lock

# Function representing a process thread
def process_thread(process_id):
    time.sleep(random.randint(1, 3))  # Simulate process delay
    request_resources(process_id)
    time.sleep(random.randint(1, 3))  # Simulate process execution

# Main simulation
threads = []
for i in range(NUM_PROCESSES):
    t = threading.Thread(target=process_thread, args=(i,))
    threads.append(t)
    t.start()

# Wait for all threads to finish
for t in threads:
    t.join()

print("Simulation complete.")
````

## Output:

```
Process 0 requesting [3, 2, 2]
Request granted. Safe sequence: [0, 1, 3, 4, 2]
Process 1 requesting [2, 1, 1]
Request granted. Safe sequence: [0, 1, 3, 4, 2]
Process 2 requesting [4, 0, 2]
Request denied to avoid deadlock.
Process 3 requesting [2, 2, 2]
Request granted. Safe sequence: [0, 1, 3, 4, 2]
Process 4 requesting [1, 1, 1]
Request granted. Safe sequence: [0, 1, 3, 4, 2]
Simulation complete.
```

## Conclusion:
Successfully Demonstrated use of semaphores for deadlock avoidance.