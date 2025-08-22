---
Title: "Operating Systems Lab 9"
Status: 
marker: 
tags: 
Date: "2025.04.02"
Time: "10:46"
---
# Semaphore usage to avoid deadlocks

### Problem Setup:

- Let's say there are two resources (R1 and R2).
- There are two threads (Thread A and Thread B) that need both resources.
- We will use semaphores to prevent deadlocks by controlling the order in which resources are requested.
### Algorithm:

1. Use two semaphores for the resources R1 and R2.
2. Each thread will try to acquire the resources.
3. If a thread cannot acquire a resource, it will release any resources it has already acquired and then try again after some time (this avoids deadlock).

### Python Code:

```python
import threading
import time

# Initialize semaphores for two resources (R1 and R2)
resource_1 = threading.Semaphore(1)  # Resource 1, initially available
resource_2 = threading.Semaphore(1)  # Resource 2, initially available

# Function to simulate deadlock avoidance with semaphores
def thread_1():
    print("Thread 1 trying to acquire Resource 1...")
    resource_1.acquire()  # Try to acquire Resource 1
    print("Thread 1 acquired Resource 1.")

    time.sleep(1)  # Simulating some operation
    
    print("Thread 1 trying to acquire Resource 2...")
    resource_2.acquire()  # Try to acquire Resource 2
    print("Thread 1 acquired Resource 2.")
    
    # Critical section
    print("Thread 1 working with both resources.")
    
    # Release the resources
    resource_2.release()
    resource_1.release()
    print("Thread 1 released both resources.")

def thread_2():
    print("Thread 2 trying to acquire Resource 1...")
    resource_1.acquire()  # Try to acquire Resource 1
    print("Thread 2 acquired Resource 1.")

    time.sleep(1)  # Simulating some operation

    print("Thread 2 trying to acquire Resource 2...")
    resource_2.acquire()  # Try to acquire Resource 2
    print("Thread 2 acquired Resource 2.")

    # Critical section
    print("Thread 2 working with both resources.")
    
    # Release the resources
    resource_2.release()
    resource_1.release()
    print("Thread 2 released both resources.")

# Create two threads
thread_1_instance = threading.Thread(target=thread_1)
thread_2_instance = threading.Thread(target=thread_2)

# Start the threads
thread_1_instance.start()
thread_2_instance.start()

# Wait for both threads to complete
thread_1_instance.join()
thread_2_instance.join()

print("Both threads have finished execution.")
```

### Explanation:

1. **Semaphore Initialization**: We initialize two semaphores, `resource_1` and `resource_2`, both set to 1 (indicating that both resources are initially available).
 2. **Thread Functions**: Both `thread_1` and `thread_2` simulate threads that require both resources:
     - **Thread 1**: Acquires `resource_1` first, then waits 1 second and acquires `resource_2`.
    - **Thread 2**: Similarly acquires `resource_1` first, waits 1 second, and then tries to acquire `resource_2`.
3. **Deadlock Avoidance**:
    - If a thread cannot acquire both resources, it will not hold onto any resource and will release what it has acquired. This prevents a situation where one thread is holding one resource and waiting indefinitely for another resource that the other thread is holding.
4. **Critical Section**: Both threads perform their work with the resources they acquire. Once done, they release the resources.

### Output:

```
Thread 1 trying to acquire Resource 1...
Thread 1 acquired Resource 1.
Thread 2 trying to acquire Resource 1...
Thread 2 acquired Resource 1.
Thread 1 trying to acquire Resource 2...
Thread 1 acquired Resource 2.
Thread 1 working with both resources.
Thread 2 trying to acquire Resource 2...
Thread 2 acquired Resource 2.
Thread 2 working with both resources.
Thread 2 released both resources.
Thread 1 released both resources.
Both threads have finished execution.
```


# References


###### Information
- date: 2025.04.02
- time: 10:46