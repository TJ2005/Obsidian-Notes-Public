### Solution:
We will implement this using **semaphores** to handle synchronization between the producer and consumer.
### Python Code (Producer-Consumer Problem with Semaphores):
```python
import threading
import time
import random

# Buffer size
BUFFER_SIZE = 5

# Shared buffer
buffer = []

# Semaphores to manage synchronization
mutex = threading.Semaphore(1)  # Ensures mutual exclusion while accessing the buffer
empty = threading.Semaphore(BUFFER_SIZE)  # Tracks empty spaces in the buffer
full = threading.Semaphore(0)  # Tracks filled slots in the buffer

# Producer function
def producer():
    global buffer
    while True:
        # Produce an item (random number for example)
        item = random.randint(1, 100)
        empty.acquire()  # Wait for an empty space
        mutex.acquire()  # Ensure exclusive access to the buffer

        buffer.append(item)  # Produce the item (add to buffer)
        print(f"Produced: {item} | Buffer: {buffer}")
        
        mutex.release()  # Release the mutex lock
        full.release()  # Signal that the buffer has a new item

        time.sleep(random.uniform(0.1, 0.5))  # Simulate production time

# Consumer function
def consumer():
    global buffer
    while True:
        full.acquire()  # Wait for a filled slot
        mutex.acquire()  # Ensure exclusive access to the buffer
        
        item = buffer.pop(0)  # Consume the item (remove from buffer)
        print(f"Consumed: {item} | Buffer: {buffer}")

        mutex.release()  # Release the mutex lock
        empty.release()  # Signal that the buffer has an empty slot

        time.sleep(random.uniform(0.1, 0.5))  # Simulate consumption time

# Main function to start producer and consumer threads
def main():
    # Create producer and consumer threads
    producer_thread = threading.Thread(target=producer)
    consumer_thread = threading.Thread(target=consumer)

    # Start the threads
    producer_thread.start()
    consumer_thread.start()

    # Wait for both threads to complete (although in an infinite loop here)
    producer_thread.join()
    consumer_thread.join()

if __name__ == "__main__":
    main()
```

### Sample Output:

```
Produced: 56 | Buffer: [56]
Consumed: 56 | Buffer: []
Produced: 91 | Buffer: [91]
Consumed: 91 | Buffer: []
Produced: 17 | Buffer: [17]
Produced: 34 | Buffer: [17, 34]
Consumed: 17 | Buffer: [34]
Produced: 9 | Buffer: [34, 9]
```
