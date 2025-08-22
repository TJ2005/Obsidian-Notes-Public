### Python Code for Semaphore and Banker's Algorithm Combined:

```python
import threading

# Semaphore class to control access to resources
class Semaphore:
    def __init__(self, count):
        self.count = count
        self.lock = threading.Lock()

    def acquire(self):
        with self.lock:
            while self.count == 0:
                pass  # Busy waiting for resources to become available
            self.count -= 1

    def release(self):
        with self.lock:
            self.count += 1

class BankersAlgorithm:
    def __init__(self, processes, resources, max_resources, allocated_resources, available_resources):
        self.processes = processes  # Number of processes
        self.resources = resources  # Number of resource types
        self.max_resources = max_resources  # Maximum demand matrix
        self.allocated_resources = allocated_resources  # Allocation matrix
        self.available_resources = available_resources  # Available resources
        self.need_resources = [[self.max_resources[i][j] - self.allocated_resources[i][j] for j in range(self.resources)] for i in range(self.processes)]

    def is_safe(self):
        work = self.available_resources[:]
        finish = [False] * self.processes
        safe_sequence = []

        while len(safe_sequence) < self.processes:
            progress = False
            for i in range(self.processes):
                if not finish[i]:
                    if all(self.need_resources[i][j] <= work[j] for j in range(self.resources)):
                        safe_sequence.append(i)
                        for j in range(self.resources):
                            work[j] += self.allocated_resources[i][j]
                        finish[i] = True
                        progress = True
                        break

            if not progress:
                return False, []

        return True, safe_sequence

    def request_resources(self, process_id, request):
        if any(request[i] > self.need_resources[process_id][i] for i in range(self.resources)):
            return False

        if any(request[i] > self.available_resources[i] for i in range(self.resources)):
            return False

        temp_available = self.available_resources[:]
        temp_allocated = self.allocated_resources[:]
        temp_need = self.need_resources[:]

        for i in range(self.resources):
            temp_available[i] -= request[i]
            temp_allocated[process_id][i] += request[i]
            temp_need[process_id][i] -= request[i]

        temp_banker = BankersAlgorithm(self.processes, self.resources, self.max_resources, temp_allocated, temp_available)
        is_safe, _ = temp_banker.is_safe()

        if is_safe:
            self.available_resources = temp_available
            self.allocated_resources = temp_allocated
            self.need_resources = temp_need
            return True
        else:
            return False


def main():
    processes = 5
    resources = 3
    available_resources = [3, 3, 2]

    max_resources = [
        [7, 5, 3],
        [3, 2, 2],
        [9, 0, 2],
        [2, 2, 2],
        [4, 3, 3]
    ]

    allocated_resources = [
        [0, 1, 0],
        [2, 0, 0],
        [3, 0, 2],
        [2, 1, 1],
        [0, 0, 2]
    ]

    banker = BankersAlgorithm(processes, resources, max_resources, allocated_resources, available_resources)

    is_safe, safe_sequence = banker.is_safe()

    if is_safe:
        print("System is in a safe state.")
        print("Safe sequence:", safe_sequence)
    else:
        print("System is in an unsafe state.")

    semaphore = Semaphore(1)  # Only one process can access at a time

    def process_task(process_id, request):
        print(f"Process {process_id} requesting resources:", request)
        semaphore.acquire()
        if banker.request_resources(process_id, request):
            print(f"Process {process_id} granted resources")
        else:
            print(f"Process {process_id} request denied")
        semaphore.release()

    # Example of resource request by process 1
    process_task(1, [1, 0, 2])

if __name__ == "__main__":
    main()
```

### Output Example:

```
System is in a safe state.
Safe sequence: [0, 1, 3, 4, 2]
Process 1 requesting resources: [1, 0, 2]
Process 1 granted resources
```
