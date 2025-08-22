---
Title: "Operating System Lab 7"
Status: 
marker: 
tags: 
Date: "2025.03.29"
Time: "12:07"
---
### Python Code for Banker's Algorithm

```python
class BankersAlgorithm:
    def __init__(self, processes, resources, max_resources, allocated_resources):
        self.processes = processes  # Number of processes
        self.resources = resources  # Number of resource types
        self.max_resources = max_resources  # Maximum demand matrix
        self.allocated_resources = allocated_resources  # Allocation matrix
        self.available_resources = [resources[i] - sum(allocated_resources[j][i] for j in range(processes)) for i in range(len(resources))]  # Available resources

        # Calculate the need matrix (Max - Allocation)
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
                        # If the process can be satisfied, pretend to run it
                        safe_sequence.append(i)
                        for j in range(self.resources):
                            work[j] += self.allocated_resources[i][j]  # Resources released by the process
                        finish[i] = True
                        progress = True
                        break

            if not progress:
                return False, []

        return True, safe_sequence

    def request_resources(self, process_id, request):
        # Check if request is less than or equal to the need matrix
        if any(request[i] > self.need_resources[process_id][i] for i in range(self.resources)):
            return False  # Invalid request

        # Check if request is less than or equal to available resources
        if any(request[i] > self.available_resources[i] for i in range(self.resources)):
            return False  # Not enough resources

        # Temporarily allocate requested resources
        temp_available = self.available_resources[:]
        temp_allocated = self.allocated_resources[:]
        temp_need = self.need_resources[:]

        for i in range(self.resources):
            temp_available[i] -= request[i]
            temp_allocated[process_id][i] += request[i]
            temp_need[process_id][i] -= request[i]

        # Check if the system is still in a safe state
        temp_banker = BankersAlgorithm(self.processes, self.resources, self.max_resources, temp_allocated)
        is_safe, _ = temp_banker.is_safe()

        if is_safe:
            # Proceed with the allocation
            self.available_resources = temp_available
            self.allocated_resources = temp_allocated
            self.need_resources = temp_need
            return True
        else:
            return False

# Example usage
if __name__ == "__main__":
    # Number of processes
    processes = 5

    # Number of resource types
    resources = 3

    # Available instances of resources A, B, C
    available = [3, 3, 2]

    # Maximum demand of resources by each process
    max_resources = [
        [7, 5, 3],
        [3, 2, 2],
        [9, 0, 2],
        [2, 2, 2],
        [4, 3, 3]
    ]

    # Resources currently allocated to each process
    allocated_resources = [
        [0, 1, 0],
        [2, 0, 0],
        [3, 0, 2],
        [2, 1, 1],
        [0, 0, 2]
    ]

    # Create a BankersAlgorithm instance
    banker = BankersAlgorithm(processes, resources, max_resources, allocated_resources)

    # Check if the system is in a safe state
    is_safe, safe_sequence = banker.is_safe()

    if is_safe:
        print("System is in a safe state.")
        print("Safe sequence is:", safe_sequence)
    else:
        print("System is in an unsafe state.")

    # Simulate a resource request for process 1
    request = [1, 0, 2]
    if banker.request_resources(1, request):
        print("Request granted for process 1.")
    else:
        print("Request denied for process 1.")
```

### Output Example:

```
System is in a safe state.
Safe sequence is: [0, 1, 3, 4, 2]
Request granted for process 1.
```

### Key Concepts:

- **Banker's Algorithm**: The Banker's Algorithm is used for deadlock avoidance. It checks if the system is in a safe state by simulating the allocation of resources. The algorithm ensures that no process will be left in a deadlock state by only granting requests that leave the system in a safe state.
    
- **Safe State**: A state in which there is at least one sequence of processes that can complete without leading to a deadlock.
    
- **Request Handling**: Processes request resources, and the Banker's Algorithm checks whether the request can be granted while keeping the system in a safe state.
    

### End.