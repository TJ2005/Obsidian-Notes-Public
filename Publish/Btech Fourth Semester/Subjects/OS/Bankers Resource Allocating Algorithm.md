---
Title: "Bankers Resource Allocating Algorithm"
Status: 
marker: 
tags: 
Date: "2025.03.01"
Time: "12:34"
---
# Bankers Resource Allocating Algorithm
### Banker's Algorithm: A Brief Overview

The Banker's Algorithm is a deadlock avoidance algorithm used in operating systems to manage resource allocation in a way that prevents deadlocks. It ensures that the system remains in a safe state, where there is always a sequence of processes that can complete and release their resources.

#### Key Concepts:

- **Safe State**: A state where there exists a sequence of processes that can finish executing without causing a deadlock.
- **Work and Finish Arrays**: `Work` simulates the available resources, and `Finish` tracks whether a process can complete execution.
- **Need Matrix**: Calculated as `Need = Max - Allocation`, representing the additional resources a process may request.

#### How It Works:

1. **Initialization**: Set `Work` to the available resources and `Finish` to `false` for all processes.
2. **Resource Allocation**: For each process, check if its `Need` is less than or equal to `Work`. If so, allocate resources and update `Work` and `Finish`.
3. **Safety Check**: Continue allocating resources until all processes can complete, ensuring the system remains in a safe state.

The Banker's Algorithm is particularly useful in environments where resource allocation must be carefully managed to avoid deadlocks, ensuring that processes can always complete their execution.
---

### Example of Banker’s Algorithm

- **Number of processes**: 5 ($P_1$ through $P_5$)
- **Resource types**:
  - $A$ (10 instances)
  - $B$ (5 instances)
  - $C$ (7 instances)

Snapshot at time $T_c$:

| Process       | Allocation | Max   | Available | Need (Calculated by students) |
| ------------- | ---------- | ----- | --------- | ----------------------------- |
|               | A B C      | A B C | A B C     | A B C                         |
| $P_1$         | 1 0 5      | 7 5 3 | 3 3 2     | 6 5 3                         |
| $P_2$         | 0 1 0      | 7 5 3 |           | 7 4 3                         |
| $P_3$         | 2 0 0      | 3 2 2 |           | 1 2 2                         |
| $P_4$         | 3 0 2      | 9 0 2 |           | 6 0 0                         |
| $P_5$         | 0 0 2      | 4 3 3 |           | 4 3 1                         |
| **Available** |            |       | 3 3 2     |                               |

#### Key Definitions:

- **Allocation**: The resources currently allocated to each process.
- **Max**: The maximum resources each process may need.
- **Available**: The resources available in the system at the given time.
- **Need**: The remaining resources required by each process to complete, calculated as:
$$  \text{Need} = \text{Max} - \text{Allocation}$$


#### Work and Finish Arrays:

- **Work**: Initially set to the Available resources, i.e., `Work = Available = [3, 3, 2]`.
- **Finish**: An array of boolean values, initially set to `false` for all processes. A value of `true` will indicate that a process can finish its execution and release resources.
  - **Finish[i]** becomes `true` if the need of process $P_i$ is less than or equal to the current `Work` resources.

#### Algorithm Steps:

1. **Initialization**: Set `Work = Available = [3, 3, 2]`, and `Finish[i] = false` for all $i$.

2. **Find a process with unmet needs**: Check each process for which `Finish[i] = false`. If the **Need** of that process is less than or equal to `Work`, it means the process can execute and release its allocated resources.

3. **Process Execution**:
   - Start with $P_1$. The **Need** for $P_1$ is [6, 5, 3], which is greater than the available resources [3, 3, 2]. Therefore, $P_1$ cannot be allocated.
   - Move to $P_2$. The **Need** for $P_2$ is [7, 4, 3], which is greater than the available resources [3, 3, 2]. Thus, $P_2$ cannot be allocated either.
   - Check $P_3$. The **Need** for $P_3$ is [1, 2, 2], which is less than the available resources [3, 3, 2]. Hence, $P_3$ can be allocated.

     After allocating $P_3$:
     - Update `Work = Work + Allocation[P_3] = [3, 3, 2] + [2, 0, 0] = [5, 3, 2]`.
     - Set `Finish[3] = true` (since $P_3$ has completed).
     - Go back to step 2.

4. **Continue the process**:
   - Now, check if any other process can be allocated. Since the resources available are now [5, 3, 2], move to $P_1$, $P_2$, $P_4$, and $P_5$ and check their **Need** values relative to `Work`.
   - Eventually, if all processes can be allocated and finished in a safe sequence, the system is in a **safe state**.

#### Dry Run:

1. **Initial State**:
   - Work = [3, 3, 2]
   - Finish = [false, false, false, false, false]

2. **Check $P_1$**:
   - Need = [6, 5, 3]
   - Need > Work, so $P_1$ cannot be allocated.

3. **Check $P_2$**:
   - Need = [7, 4, 3]
   - Need > Work, so $P_2$ cannot be allocated.

4. **Check $P_3$**:
   - Need = [1, 2, 2]
   - Need ≤ Work, so $P_3$ can be allocated.
   - Update Work = [5, 3, 2]
   - Set Finish[3] = true

5. **Check $P_4$**:
   - Need = [6, 0, 0]
   - Need ≤ Work, so $P_4$ can be allocated.
   - Update Work = [8, 3, 4]
   - Set Finish[4] = true

6. **Check $P_5$**:
   - Need = [4, 3, 1]
   - Need ≤ Work, so $P_5$ can be allocated.
   - Update Work = [8, 6, 6]
   - Set Finish[5] = true

7. **Check $P_1$ again**:
   - Need = [6, 5, 3]
   - Need ≤ Work, so $P_1$ can be allocated.
   - Update Work = [14, 11, 11]
   - Set Finish[1] = true

8. **Check $P_2$ again**:
   - Need = [7, 4, 3]
   - Need ≤ Work, so $P_2$ can be allocated.
   - Update Work = [14, 15, 11]
   - Set Finish[2] = true

#### Final State:

- All processes have been allocated and finished successfully.
- The system is in a **safe state**.

#### Final Remarks:

The **Banker's Algorithm** ensures that the system avoids unsafe states by checking if there is always a way to allocate resources such that every process can eventually finish and release its resources. If such a sequence exists, the system is in a safe state.

---

### Resource Allocation Algorithm

First, let's examine the table:

| Process ID | Allocation | Max | Available | Need = $Max - Allocation$ |
| ---------- | ---------- | --- | --------- | ------------------------- |
| P0         | 0 1 0      | 7 5 3 | 3 3 2     | 7 4 3                     |
| P1         | 2 0 0      | 3 2 2 |           | 1 2 2                     |
| P2         | 3 0 2      | 9 0 2 |           | 6 0 0                     |
| P3         | 2 1 1      | 2 2 2 |           | 0 1 1                     |
| P4         | 0 0 2      | 4 3 3 |           | 4 3 1                     |

#### Steps to Determine Resource Allocation:

1. If the `request` is greater than the `need`, go to step 2.
2. If the `request` is less than or equal to `Available`:
   - Update the allocation: `allocation = allocation + request`.
   - Update the need: `Need = Need - request`.

#### Dry Run:

1. **Initial State**:
   - Work = [3, 3, 2]
   - Finish = [false, false, false, false, false]

2. **Check $P_0$**:
   - Need = [7, 4, 3]
   - Need > Work, so $P_0$ cannot be allocated.

3. **Check $P_1$**:
   - Need = [1, 2, 2]
   - Need ≤ Work, so $P_1$ can be allocated.
   - Update Work = [5, 3, 2]
   - Set Finish[1] = true

4. **Check $P_2$**:
   - Need = [6, 0, 0]
   - Need ≤ Work, so $P_2$ can be allocated.
   - Update Work = [8, 3, 4]
   - Set Finish[2] = true

5. **Check $P_3$**:
   - Need = [0, 1, 1]
   - Need ≤ Work, so $P_3$ can be allocated.
   - Update Work = [8, 4, 5]
   - Set Finish[3] = true

6. **Check $P_4$**:
   - Need = [4, 3, 1]
   - Need ≤ Work, so $P_4$ can be allocated.
   - Update Work = [12, 7, 6]
   - Set Finish[4] = true

7. **Check $P_0$ again**:
   - Need = [7, 4, 3]
   - Need ≤ Work, so $P_0$ can be allocated.
   - Update Work = [19, 11, 9]
   - Set Finish[0] = true

#### Final State:

| Process ID | Allocation | Max   | Available | Need = $Max - Allocation$ |
| ---------- | ---------- | ----- | --------- | ------------------------- |
| P0         | 0 1 0      | 7 5 3 | 3 3 2     | 7 4 3                     |
| P1         | 2 0 0      | 3 2 2 |           | 1 2 2                     |
| P2         | 3 0 2      | 9 0 2 |           | 6 0 0                     |
| P3         | 2 1 1      | 2 2 2 |           | 0 1 1                     |
| P4         | 0 0 2      | 4 3 3 |           | 4 3 1                     |
### Mermaid Diagram and Complete answer

```mermaid
flowchart TD
    A[Start] --> B[Initialize Work and Finish]
    B --> C{Check each process}
    C --> D{Is Finish false?}
    D -- Yes --> E{Is Need[i] <= Work?}
    E -- Yes --> F[Allocate resources to process i]
    F --> G[Update Work = Work + Allocation[i]]
    G --> H[Set Finish[i] to true]
    H --> C
    E -- No --> C
    D -- No --> I{Are all processes checked?}
    I -- No --> C
    I -- Yes --> J[End: Safe State]

```
- Safety Index
	-  $P_1$ , $P_3$, $P_4$, $P_2$, $P_0$
- All processes have been allocated and finished successfully.
- The system is in a **safe state**.

---

This detailed dry run demonstrates how both the Banker's Algorithm and the Resource Allocation Algorithm work step-by-step to ensure safe resource allocation.


# References


###### Information
- date: 2025.03.01
- time: 12:34