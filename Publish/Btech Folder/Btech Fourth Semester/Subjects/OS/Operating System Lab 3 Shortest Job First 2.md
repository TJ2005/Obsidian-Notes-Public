---
Title: Operating System Lab 3
Status: 
marker: 
tags: 
Date: 2025.01.29
Time: 10:16
---
## Practical 3: Shortest Job First Scheduling Algorithm
**Objective**:  
To implement and compute the **Turnaround Time** and **Waiting Time** for the **Shortest Job First (SJF)** scheduling algorithm. The following steps will be covered:

1. **Completion Time**: The time when the process finishes execution.
2. **Turnaround Time (TAT)**: Difference between completion time and arrival time. TAT=CompletionTime−ArrivalTimeTAT = Completion Time - Arrival Time
3. **Waiting Time (WT)**: Difference between turnaround time and burst time. WT=TAT−BurstTimeWT = TAT - Burst Time

---

### **Code Explanation**:

Here’s the Python code to implement the Shortest Job First (SJF) scheduling algorithm:

```python
def main():
    n = int(input("Enter number of processes: "))  # Number of processes
    bt = []  # Burst times
    p = []   # Process IDs
    wt = []  # Waiting times
    tat = [] # Turnaround times
    at = []  # Arrival times
    total_wt = 0  # Total waiting time
    total_tat = 0 # Total turnaround time

    print("\nEnter Burst Time:")
    for i in range(n):
        bt.append(int(input(f"P{i+1}: ")))  # Getting burst times for each process
        p.append(i+1)  # Process IDs

    print("\n\nEnter Arrival Time:")
    for i in range(n):
        at.append(int(input(f"P{i+1}: ")))  # Getting arrival times for each process

    # Sorting burst times in ascending order
    for i in range(n):
        pos = i
        for j in range(i+1, n):
            if bt[j] < bt[pos]:
                pos = j
        bt[i], bt[pos] = bt[pos], bt[i]  # Swap burst time
        p[i], p[pos] = p[pos], p[i]  # Swap process IDs

    # Calculating Waiting Times
    wt.append(0)  # The first process has no waiting time
    for i in range(1, n):
        wt.append(0)  # Initialize waiting times
        for j in range(i):
            wt[i] += bt[j]  # Add burst time of all previous processes
        total_wt += wt[i]

    avg_wt = total_wt / n  # Average waiting time

    # Calculating Turnaround Times
    print("\nProcess\t    Burst Time    \t Waiting Time\t Turnaround Time\t Arrival Time")
    for i in range(n):
        tat.append(bt[i] + wt[i])  # Turnaround time = burst time + waiting time
        total_tat += tat[i]
        print(f"P{p[i]}\t\t  {bt[i]}\t\t    {wt[i]}\t\t\t{tat[i]}\t\t\t{at[i]}")

    avg_tat = total_tat / n  # Average turnaround time

    print(f"\nAverage Waiting Time={avg_wt:.2f}")
    print(f"Average Turnaround Time={avg_tat:.2f}")

    # Adding your name and roll number to the output
    print("\n\nName: Sumit Pandey")
    print("Roll No: K044")

if __name__ == "__main__":
    main()
```

### **Explanation**:

1. **Input**: The program accepts burst times and arrival times for each process.
2. **Process Sorting**: The processes are sorted based on the burst times in ascending order, which is the key feature of the SJF algorithm.
3. **Waiting Time Calculation**: For each process, the waiting time is calculated as the sum of burst times of all previous processes.
4. **Turnaround Time Calculation**: The turnaround time is the sum of the burst time and the waiting time for each process.
5. **Output**: The program prints the details of each process, including its burst time, waiting time, turnaround time, and arrival time, along with the average waiting and turnaround times.

---

### **Example Input**:

```plaintext
Enter number of processes: 4

Enter Burst Time:
P1: 6
P2: 2
P3: 8
P4: 3

Enter Arrival Time:
P1: 0
P2: 1
P3: 2
P4: 3
```

### **Example Output**:
![[IMG-20250730000528830.png]]
![[IMG-20250730000544264.png]]

### **Gantt Chart**:
![[IMG-20250730000601582.png]]


---

### **Conclusion**:

- The **Shortest Job First (SJF)** algorithm works by scheduling the process with the shortest burst time next. This reduces the average waiting time and turnaround time compared to other scheduling algorithms.
    
- **Advantages over FCFS**:
    - **SJF** leads to better performance because shorter processes are executed first, which minimizes the average waiting time.
    - **FCFS** can lead to the "convoy effect," where long processes block shorter ones, increasing waiting times.

---

# References


###### Information
- date: 2025.01.29
- time: 10:16