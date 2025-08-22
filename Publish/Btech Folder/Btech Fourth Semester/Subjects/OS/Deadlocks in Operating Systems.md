---
Title: "Deadlocks in Operating Systems"
Status: 
marker: 
tags: 
Date: "2025.02.15"
Time: "12:34"
---
# Deadlocks
In environments where multiple processes run together they compete for **finite** resource. If a **Process** needs some resources that are not available it goes in a **waiting state**. The resources requested perhaps are not available due to them being occupied by **Other Waiting Processes**. Due to this the first process we talked about is in the situation of **Deadlock**.

# System Model
Contains finite number of resources 
to be distributed among proceses
resources division into types/classes fairly.

Two CPU = two instances 

If process requests instance of a specific type ANY instance of that type should be eligible to cater that process. 
If not it is not identical

For example, a system may have two printers. These two printers may be defined to be in the same resource class if no one cares which printer prints which output. However, if one printer is on the ninth floor and the other is in the basement, then people on the ninth floor may not see both printers as equivalent, and separate resource classes may need to be defined for each printer.

process must request a resource before using & must release the resource after using it
Process can request as much as they require to carry out the designated tasks but less than the total available resources.

Under the normal mode of operation, a process may utilize a resource in only the following sequence:
- **Request**: Process request does not always mean immediate grant. Requesting process must wait until it gets it
- **Use**: The process is granted the resource and it is using the resource
- **Release:** The process releases the resource as it has used the process 

Examples are the request() and release() device, open() and close() file, and allocate() and free()
 wait() and signal() operations on semaphores or through acquire() and release() of a mutex lock

Kernel manages almost all the resources
for all the resources that kernel manages it must guarantee that the process got the resource and has proper allocation
Theres a table of dbms 


# Characterization of deadlock
- Mutual Excusion : Only one process at a time can use a resource
- Hold and wait: a process at least one resource is waitng to acquire additional resources held by other processes
- No pre emption : A resource can be released only voluntarily by the process holding it after that process has completed it task.
- Circular wait: There exist a set of waiting processes such that $P_0$ is waiting for a resource that is held by $P_1$ and its waiting for a resource held by $P_2$ and so on

Deadlock can also happen due to system calls

## Deadlock Safe, Unsafe, Deadlock State

![[IMG-20250730000528796.png|center]]
# Example of Banker’s Algorithm

- 5 processes \( P_1 \) through \( P_5 \)
- 3 resource types:  
  - A (10 instances)
  - B (5 instances)
  - C (7 instances)

Snapshot at time \( T_c \):

| Process       | Allocation | Max   | Available | Need ( Calculated by students ) |
| ------------- | ---------- | ----- | --------- | ------------------------------- |
|               | A B C      | A B C | A B C     | ABC                             |
| \( P_1 \)     | 1 0 5      | 7 5 3 | 3 3 2     | 743                             |
| \( P_2 \)     | 0 1 0      | 7 5 3 |           |                                 |
| \( P_3 \)     | 2 0 0      | 3 2 2 |           |                                 |
| \( P_4 \)     | 3 0 2      | 9 0 2 |           |                                 |
| \( P_5 \)     | 0 0 2      | 4 3 3 |           |                                 |
| **Available** |            |       | 3 3 2     |                                 |

work = available 332
finish[i]=false for i=0,.... n-1
here i represents the processes id
it will be true only under the condition when the need<=work(available)

after that
find finish[i]=false
need <=work(available)

P_0 Needs 743 which is greater than 332 thus it cannot be allocated
We move to P_1 which needs 122 which is lesser than 332 thus can be allocated
work = work + allocation
finish[i]=true;

go to step 2

Here’s a clearer explanation of the Banker’s Algorithm example written in a more structured and understandable note:

---

### Example of Banker’s Algorithm

- **Number of processes**: 5 ($P_1$ through $P_5$)
- **Resource types**:
    - $A$ (10 instances)
    - $B$ (5 instances)
    - $C$(7 instances)

Snapshot at time $T_c$:

| Process       | Allocation | Max   | Available | Need (Calculated by students) |
| ------------- | ---------- | ----- | --------- | ----------------------------- |
|               | A B C      | A B C | A B C     | A B C                         |
| $P_1$         | 1 0 5      | 7 5 3 | 3 3 2     | 7 4 3                         |
| $P_2$         | 0 1 0      | 7 5 3 |           | 7 4 3                         |
| $P_3$         | 2 0 0      | 3 2 2 |           | 1 2 2                         |
| $P_{4}$       | 3 0 2      | 9 0 2 |           | 6 0 0                         |
| $P_5$         | 0 0 2      | 4 3 3 |           | 4 3 1                         |
| **Available** |            |       | 3 3 2     |                               |

#### Key Definitions:

- **Allocation**: The resources currently allocated to each process.
    
- **Max**: The maximum resources each process may need.
    
- **Available**: The resources available in the system at the given time.
    
- **Need**: The remaining resources required by each process to complete, calculated as:
    
    Need=Max−Allocation\text{Need} = \text{Max} - \text{Allocation}

#### Work and Finish Arrays:

- **Work**: Initially set to the Available resources, i.e., `Work = Available = [3, 3, 2]`.
- **Finish**: An array of boolean values, initially set to `false` for all processes. A value of `true` will indicate that a process can finish its execution and release resources.
    - **Finish[i]** becomes `true` if the need of process $P_i$ is less than or equal to the current `Work` resources.

#### Algorithm Steps:

1. **Initialization**: Set `Work = Available = [3, 3, 2]`, and `Finish[i] = false` for all ii.
    
2. **Find a process with unmet needs**: Check each process for which `Finish[i] = false`. If the **Need** of that process is less than or equal to `Work`, it means the process can execute and release its allocated resources.
    
3. **Process Execution**:
    
    - Start with $P_1$. The **Need** for $P_1$ is [7, 4, 3], which is greater than the available resources [3, 3, 2]. Therefore, $P_1$ cannot be allocated.
        
    - Move to $P_2$. The **Need** for $P_2$ is [7, 4, 3], which is greater than the available resources [3, 3, 2]. Thus, $P_2$ cannot be allocated either.
        
    - Check $P_3$. The **Need** for $P_3$ is [1, 2, 2], which is less than the available resources [3, 3, 2]. Hence, $P_3$ can be allocated.
        
        After allocating $P_3$:
        
        - Update `Work = Work + Allocation[P_3] = [3, 3, 2] + [2, 0, 0] = [5, 3, 2]`.
        - Set `Finish[3] = true` (since $P_3$ has completed).
        - Go back to step 2.
4. **Continue the process**:
    
    - Now, check if any other process can be allocated. Since the resources available are now [5, 3, 2], move to $P_1$, $P_2$, $P_4$, and $P_5$ and check their **Need** values relative to `Work`.
        
    - Eventually, if all processes can be allocated and finished in a safe sequence, the system is in a **safe state**.
        

#### Final Remarks:

The **Banker's Algorithm** ensures that the system avoids unsafe states by checking if there is always a way to allocate resources such that every process can eventually finish and release its resources. If such a sequence exists, the system is in a safe state.

---
## Resource Result Algorithm
First we have a look at the table

| Process ID | Allocation | Max | Available | Need = $Max - Allocation$ |
| ---------- | ---------- | --- | --------- | ------------------------- |
| P0         | 010        | 753 | 332       | 7433                      |
| P1         | 200        | 332 | 230       | 122                       |
| P2         | 302        | 902 |           | 600                       |
| P3         | 211        | 222 |           | 011                       |
| P4         | 002        | 433 |           | 431                       |
## Steps to produce answer

1. If $request$ $>$ $need$ go to step 2
2. If $request$ $\leq$ $Available$
   $\text{allocation}=\text{allocation}+request$
3. $\text{Need = Need - request}$

Now the dry run
1. need


# References


###### Information
- date: 2025.02.15
- time: 12:34