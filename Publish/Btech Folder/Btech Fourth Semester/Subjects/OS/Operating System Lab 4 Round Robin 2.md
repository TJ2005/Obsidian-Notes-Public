---
Title: Operating System Lab 4
Status: 
marker:
  - "[[Lab]]"
  - "[[OS Researchpaper]]"
  - "[[Operating Systems]]"
tags: 
Date: 2025.01.22
Time: 10:23
---
# Operating System Lab 4
## Question 1
```python
# Define the process class

class Process:

    def __init__(self, pid, arrival_time, burst_time):

        self.pid = pid

        self.arrival_time = arrival_time

        self.burst_time = burst_time

        self.remaining_time = burst_time

        self.completion_time = 0

        self.turnaround_time = 0

        self.waiting_time = 0

  

# Function to find the completion time of each process using Round Robin scheduling

def find_completion_time(processes, time_quantum):

    ## CPU Initializes at 0

    current_time = 0

    ## Queue Initialized for the process

    queue = []

    ## Looping through the process to append it to the queue

    for process in processes:

        queue.append(process)

    ## While the queue is not empty the while loop will run

    while queue:

        ## Pop the first / First of the remnant processes

        process = queue.pop(0)

        ## If the process remaining time is greater than the time quantum

        if process.remaining_time > time_quantum:

            ## Current time = current time + time quantum since the process is running

            current_time += time_quantum

            ## Subtract the process remaining time by the time quantum since the process has executed

            process.remaining_time -= time_quantum

            ## Append the process back to the queue since it was popped

            queue.append(process)

        else:

            ## If the process remaining time is less than the time quantum

            current_time += process.remaining_time

            ## Remaining time is set to 0 since the process has executed

            process.remaining_time = 0

            ## Completion time is set to the current time

            process.completion_time = current_time

  

# Function to find the turnaround time of each process

def find_turnaround_time(processes):

    ## Looping through the processes to find the turnaround time

    for process in processes:

        ## Process turnaround time is the difference between the completion time and the arrival time

        process.turnaround_time = process.completion_time - process.arrival_time

  

# Function to find the waiting time of each process

def find_waiting_time(processes):

    ## Looping through the processes to find the waiting time

    for process in processes:

        ## Process waiting time is the difference between the turnaround time and the burst time

        process.waiting_time = process.turnaround_time - process.burst_time

  

# Function to find the average turnaround time

def find_average_turnaround_time(processes):

    ## Looping through the processes to find the average turnaround time

    total_turnaround_time = sum(process.turnaround_time for process in processes)

  

    return total_turnaround_time / len(processes)

  

# Function to find the average waiting time

def find_average_waiting_time(processes):

    total_waiting_time = sum(process.waiting_time for process in processes)

    return total_waiting_time / len(processes)

  

# Main function

def main():

    # Define the processes with their arrival time and burst time

    processes = [

        Process(1, 0, 5),

        Process(2, 1, 3),

        Process(3, 2, 1),

        Process(4, 3, 2),

        Process(5, 4, 3)

    ]

  

    # Define the time quantum

    time_quantum = 2

  

    # Calculate completion, turnaround, and waiting times

    find_completion_time(processes, time_quantum)

    find_turnaround_time(processes)

    find_waiting_time(processes)

  

    # Print the results

    print("Process ID\tArrival Time\tBurst Time\tCompletion Time\tTurnaround Time\tWaiting Time")

    for process in processes:

        print(f"{process.pid}\t\t{process.arrival_time}\t\t{process.burst_time}\t\t{process.completion_time}\t\t{process.turnaround_time}\t\t{process.waiting_time}")

  

    # Calculate and print average turnaround and waiting times

    avg_turnaround_time = find_average_turnaround_time(processes)

    avg_waiting_time = find_average_waiting_time(processes)

    print(f"\nAverage Turnaround Time: {avg_turnaround_time}")

    print(f"Average Waiting Time: {avg_waiting_time}")

  

if __name__ == "__main__":

    main()

    print("Tejas Sahoo k057")
```

![[IMG-20250730000528838.png]]
## Question 2
```python
from gantChart import display_round_robin_chart

  

# Define the process class

class Process:

    def __init__(self, pid, arrival_time, burst_time):

        # Initialize process ID, arrival time, burst time, remaining time, completion time, turnaround time, and waiting time

        self.pid = pid

        self.arrival_time = arrival_time

        self.burst_time = burst_time

        self.remaining_time = burst_time

        self.completion_time = 0

        self.turnaround_time = 0

        self.waiting_time = 0

  

# Function to find the completion time of each process using Round Robin scheduling

def find_completion_time(processes, time_quantum):

    current_time = 0  # Initialize the current time to 0

    queue = []  # Initialize an empty queue to hold processes

    for process in processes:

        queue.append(process)  # Add all processes to the queue

    while queue:  # Continue until the queue is empty

        process = queue.pop(0)  # Get the first process in the queue

        if process.remaining_time > time_quantum:  # If the remaining time of the process is greater than the time quantum

            current_time += time_quantum  # Increment the current time by the time quantum

            process.remaining_time -= time_quantum  # Decrease the remaining time of the process by the time quantum

            queue.append(process)  # Add the process back to the end of the queue

        else:  # If the remaining time of the process is less than or equal to the time quantum

            current_time += process.remaining_time  # Increment the current time by the remaining time of the process

            process.remaining_time = 0  # Set the remaining time of the process to 0

            process.completion_time = current_time  # Set the completion time of the process to the current time

  

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

    # Define a list of processes with their process ID, arrival time, and burst time

    processes = [

        Process(1, 0, 4),

        Process(2, 1, 5),

        Process(3, 2, 2),

        Process(4, 3, 1),

        Process(5, 4, 6),

        Process(5, 6, 3 )

    ]

  

    time_quantum = 2  # Define the time quantum for Round Robin scheduling

  

    # Calculate completion time, turnaround time, and waiting time for each process

    find_completion_time(processes, time_quantum)

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

            "waiting_time": process.waiting_time

        })

  

    # Calculate the average turnaround time and average waiting time

    avg_turnaround_time = find_average_turnaround_time(processes)

    avg_waiting_time = find_average_waiting_time(processes)

  

    # Append the average turnaround time and average waiting time to the results list

    print({

        "average_turnaround_time": avg_turnaround_time,

        "average_waiting_time": avg_waiting_time

    })

  

    return results  # Return the results list

  

if __name__ == "__main__":

    results = main()  # Call the main function and store the results

    for result in results:

        print(result)  # Print each result in the results list

    print("Tejas Sahoo k057")

    display_round_robin_chart(results,2)
```
![[IMG-20250730000545064.png]]

# References


###### Information
- date: 2025.01.22
- time: 10:23