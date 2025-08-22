---
Title: "Operating System Lab 5"
Status: 
marker: 
tags: 
Date: "2025.02.19"
Time: "10:34"
---
# Priority Scheduling

Priority scheduling is a fundamental scheduling algorithm used in operating systems to manage the execution of processes based on their assigned priorities. It is particularly useful in batch systems and real-time environments where certain tasks need to be prioritized over others.
## Application Case

Priority scheduling is commonly used in:
- **Real-time Systems**: Ensuring critical tasks are executed promptly.
- **Operating Systems**: Managing system and user processes based on importance.
- **Task Management Software**: Prioritizing tasks based on urgency or importance.

## Benefits of Priority Scheduling

- **Efficient Resource Allocation**: Ensures that critical processes are executed first, optimizing resource use.
- **Improved System Responsiveness**: High-priority tasks are completed faster, enhancing system performance.
- **Flexibility**: Allows dynamic adjustment of priorities based on system requirements.

## Cons of Priority Scheduling

- **Starvation**: Low-priority processes may never get executed if high-priority processes continuously arrive.
- **Complexity**: Requires careful management of priorities to avoid starvation and ensure fairness.
---
# Preemptive vs. Non-Preemptive Priority Scheduling

Priority scheduling can be implemented in two ways: preemptive and non-preemptive.
## Preemptive Priority Scheduling

### Definition
In preemptive priority scheduling, a higher-priority process can interrupt the execution of a lower-priority process. This means that if a higher-priority process arrives while a lower-priority process is running, the lower-priority process is paused, and the higher-priority process is executed immediately.

### Application Case
- **Real-time Systems**: Critical tasks can interrupt ongoing processes to ensure timely execution.
- **Multitasking Operating Systems**: Enhances responsiveness by allowing urgent tasks to preempt less critical ones.

### Benefits
- **Enhanced Responsiveness**: High-priority tasks are executed without delay.
- **Better Utilization of CPU**: Idle time is minimized as high-priority tasks are processed immediately.

### Cons
- **Overhead**: Context switching can lead to increased overhead.
- **Complexity**: Requires sophisticated mechanisms to handle interruptions and context switching.

## Non-Preemptive Priority Scheduling

### Definition
In non-preemptive priority scheduling, once a process starts executing, it runs to completion or until it voluntarily yields the CPU. Higher-priority processes must wait until the current process finishes execution.

### Application Case
- **Batch Systems**: Suitable for environments where tasks can be queued and executed sequentially.
- **Simple Embedded Systems**: Where the overhead of context switching is undesirable.

### Benefits
- **Simplicity**: Easier to implement and manage compared to preemptive scheduling.
- **Reduced Overhead**: Minimal context switching leads to lower overhead.

### Cons
- **Lower Responsiveness**: High-priority tasks may have to wait for lower-priority tasks to complete.
- **Potential for Long Wait Times**: Low-priority processes may experience extended wait times.

---
# Comparison Table

| Feature            | Preemptive Priority Scheduling                   | Non-Preemptive Priority Scheduling           |
| ------------------ | ------------------------------------------------ | -------------------------------------------- |
| **Interruption**   | Allows interruption of lower-priority processes  | No interruption; processes run to completion |
| **Responsiveness** | High; immediate execution of high-priority tasks | Lower; high-priority tasks may wait          |
| **Complexity**     | Higher; requires context switching mechanisms    | Lower; simpler implementation                |
| **Overhead**       | Higher due to context switching                  | Lower; minimal context switching             |
| **Suitability**    | Real-time systems, multitasking OS               | Batch systems, simple embedded systems       |

Priority scheduling, whether preemptive or non-preemptive, is a crucial concept in managing process execution efficiently, balancing responsiveness, and resource utilization based on the system's requirements.

---
# Non Pre-emptive Priority scheduling
```python
from gantChart import display_process_scheduling_chart

  

# Define the process class

class Process:

    def __init__(self, pid, arrival_time, burst_time, priority):

        self.pid = pid

        self.arrival_time = arrival_time

        self.burst_time = burst_time

        self.remaining_time = burst_time

        self.completion_time = 0

        self.turnaround_time = 0

        self.waiting_time = 0

        self.priority = priority

  

# Function to find completion time (non-preemptive priority)

def find_completion_time(processes):

    # Sort processes by arrival time first, and by priority second

    processes.sort(key=lambda x: (x.arrival_time, x.priority))

  

    current_time = 0

    completed = 0

    n = len(processes)

    while completed < n:

        # Select the process with the highest priority that has arrived

        ready_processes = [p for p in processes if p.arrival_time <= current_time and p.completion_time == 0]

  

        if ready_processes:

            # Sort ready processes by priority (lowest number means highest priority)

            ready_processes.sort(key=lambda x: x.priority)

            # Select the one with highest priority

            process = ready_processes[0]

            # Set the completion time

            process.completion_time = current_time + process.burst_time

            current_time = process.completion_time

            completed += 1

        else:

            # If no processes are ready, move time forward to the next arriving process

            current_time = min([p.arrival_time for p in processes if p.completion_time == 0])

  

# Function to find the turnaround time of each process

def find_turnaround_time(processes):

    for process in processes:

        process.turnaround_time = process.completion_time - process.arrival_time

  

# Function to find the waiting time of each process

def find_waiting_time(processes):

    for process in processes:

        process.waiting_time = process.turnaround_time - process.burst_time

  

# Function to find the average turnaround time

def find_average_turnaround_time(processes):

    total_turnaround_time = sum(process.turnaround_time for process in processes)

    return total_turnaround_time / len(processes)

  

# Function to find the average waiting time

def find_average_waiting_time(processes):

    total_waiting_time = sum(process.waiting_time for process in processes)

    return total_waiting_time / len(processes)

  

# Main function

def main():

    # Define a list of processes with their process ID, arrival time, burst time, and priority

    processes = [

        Process("P1", 0, 11, 2),

        Process("P2", 5, 28, 0),

        Process("P3", 12, 2, 3),

        Process("P4", 2, 10, 1),

        Process("P5", 9, 16, 4)

    ]

  

    # Calculate completion time, turnaround time, and waiting time for each process

    find_completion_time(processes)

    find_turnaround_time(processes)

    find_waiting_time(processes)

  

    results = []

    for process in processes:

        results.append({

            "pid": process.pid,

            "arrival_time": process.arrival_time,

            "burst_time": process.burst_time,

            "completion_time": process.completion_time,

            "turnaround_time": process.turnaround_time,

            "waiting_time": process.waiting_time,

            "priority": process.priority

        })

  

    # Calculate the average turnaround time and average waiting time

    avg_turnaround_time = find_average_turnaround_time(processes)

    avg_waiting_time = find_average_waiting_time(processes)

  

    # Print the average turnaround time and average waiting time

    print({

        "average_turnaround_time": avg_turnaround_time,

        "average_waiting_time": avg_waiting_time

    })

  

    return results

  

if __name__ == "__main__":

    results = main()

    for result in results:

        print(result)

    display_process_scheduling_chart(results)

print(result)
```

### Output
```bash
C:\Users\TJ\prog\temp\OS>python PriorityScheduling.py
{'average_turnaround_time': 37.8, 'average_waiting_time': 24.4}
{'pid': 'P1', 'arrival_time': 0, 'burst_time': 11, 'completion_time': 11, 'turnaround_time': 11, 'waiting_time': 0, 'priority': 2}
{'pid': 'P4', 'arrival_time': 2, 'burst_time': 10, 'completion_time': 49, 'turnaround_time': 47, 'waiting_time': 37, 'priority': 1}
{'pid': 'P2', 'arrival_time': 5, 'burst_time': 28, 'completion_time': 39, 'turnaround_time': 34, 'waiting_time': 6, 'priority': 0}
{'pid': 'P5', 'arrival_time': 9, 'burst_time': 16, 'completion_time': 67, 'turnaround_time': 58, 'waiting_time': 42, 'priority': 4}
{'pid': 'P3', 'arrival_time': 12, 'burst_time': 2, 'completion_time': 51, 'turnaround_time': 39, 'waiting_time': 37, 'priority': 3}
```
![[IMG-20250730000528837.png]]

# Pre-emptive Priority Scheduling
```python
from gantChart import display_process_scheduling_chart

  

# Define the process class

class Process:

    def __init__(self, pid, arrival_time, burst_time, priority):

        # Initialize process ID, arrival time, burst time, remaining time, completion time, turnaround time, waiting time, and priority

        self.pid = pid

        self.arrival_time = arrival_time

        self.burst_time = burst_time

        self.remaining_time = burst_time

        self.completion_time = 0

        self.turnaround_time = 0

        self.waiting_time = 0

        self.priority = priority

  

def find_completion_time(processes):

    current_time = 0  # Initialize the current time to 0

    completed_processes = 0  # Initialize the count of completed processes to 0

    n = len(processes)  # Get the number of processes

  

    while completed_processes < n:  # Continue until all processes are completed

        # Filter processes that have arrived and are not completed

        available_processes = [p for p in processes if p.arrival_time <= current_time and p.remaining_time > 0]

        if available_processes:

            # Select the process with the highest priority (lowest priority number)

            current_process = min(available_processes, key=lambda x: x.priority)

            # Execute the selected process for one time unit

            current_process.remaining_time -= 1

            current_time += 1

            # If the process is completed, update its completion time

            if current_process.remaining_time == 0:

                current_process.completion_time = current_time

                completed_processes += 1

        else:

            # If no process is available, increment the current time

            current_time += 1

  

# Function to find the turnaround time of each process

def find_turnaround_time(processes):

    for process in processes:

        process.turnaround_time = process.completion_time - process.arrival_time  # Calculate turnaround time as completion time minus arrival time

  

# Function to find the waiting time of each process

def find_waiting_time(processes):

    for process in processes:

        process.waiting_time = process.turnaround_time - process.burst_time  # Calculate waiting time as turnaround time minus burst time

  

# Function to find the average turnaround time

def find_average_turnaround_time(processes):

    total_turnaround_time = sum(process.turnaround_time for process in processes)  # Sum of all turnaround times

    return total_turnaround_time / len(processes)  # Calculate average turnaround time

  

# Function to find the average waiting time

def find_average_waiting_time(processes):

    total_waiting_time = sum(process.waiting_time for process in processes)  # Sum of all waiting times

    return total_waiting_time / len(processes)  # Calculate average waiting time

  

# Main function

def main():

    # Define a list of processes with their process ID, arrival time, burst time, and priority

    processes = [

        Process("P1", 0, 11, 2),

        Process("P2", 5, 28, 0),

        Process("P3", 12, 2, 3),

        Process("P4", 2, 10, 1),

        Process("P5", 9, 16, 4)

    ]

  

    # Calculate completion time, turnaround time, and waiting time for each process

    find_completion_time(processes)

    find_turnaround_time(processes)

    find_waiting_time(processes)

  

    results = []  # Initialize an empty list to store the results

    for process in processes:

        # Append the details of each process to the results list

        results.append({

            "pid": process.pid,

            "arrival_time": process.arrival_time,

            "burst_time": process.burst_time,

            "completion_time": process.completion_time,

            "turnaround_time": process.turnaround_time,

            "waiting_time": process.waiting_time,

            "priority": process.priority

        })

  

    # Calculate the average turnaround time and average waiting time

    avg_turnaround_time = find_average_turnaround_time(processes)

    avg_waiting_time = find_average_waiting_time(processes)

  

    # Print the average turnaround time and average waiting time

    print({

        "average_turnaround_time": avg_turnaround_time,

        "average_waiting_time": avg_waiting_time

    })

  

    return results  # Return the results list

  

if __name__ == "__main__":

    results = main()  # Call the main function and store the results

    for result in results:

        print(result)  # Print each result in the results list

    display_process_scheduling_chart(results)  # Display the Gantt chart
```

### Output
```bash
C:\Users\TJ\prog\temp\OS>python preemptivepriorityscheduling.py
{'average_turnaround_time': 42.4, 'average_waiting_time': 29.0}
{'pid': 'P1', 'arrival_time': 0, 'burst_time': 11, 'completion_time': 49, 'turnaround_time': 49, 'waiting_time': 38, 'priority': 2}
{'pid': 'P2', 'arrival_time': 5, 'burst_time': 28, 'completion_time': 33, 'turnaround_time': 28, 'waiting_time': 0, 'priority': 0}
{'pid': 'P3', 'arrival_time': 12, 'burst_time': 2, 'completion_time': 51, 'turnaround_time': 39, 'waiting_time': 37, 'priority': 3}
{'pid': 'P4', 'arrival_time': 2, 'burst_time': 10, 'completion_time': 40, 'turnaround_time': 38, 'waiting_time': 28, 'priority': 1}
{'pid': 'P5', 'arrival_time': 9, 'burst_time': 16, 'completion_time': 67, 'turnaround_time': 58, 'waiting_time': 42, 'priority': 4}
```
![[IMG-20250730000544766.png]]

# References


###### Information
- date: 2025.02.19
- time: 10:34