---
Title: "Operating System Lab 8"
Status: 
marker: 
tags: 
Date: "2025.03.29"
Time: "12:08"
---
# Dining Philosopher Problem Using Semaphores 

## Algorithm
Lab-8 - Dining-Philosophers problem.
Step 1: Start
Step 2: Define the number of philosophers
Step 3: Declare one thread per philosopher
Step 4: Declare one semaphore (represent chopsticks) per philosopher
Step 5: When a philosopher is hungry
See if chopsticks on both sides are free
Acquire both chopsticks
Eat
Restore the chopstick
If chopsticks aren‟t free
Step 6: Wait till they are available

### Code

```python
import threading
import time
import random

def initialize_chopsticks(num_philosophers):
    return [threading.Semaphore(1) for _ in range(num_philosophers)]

def get_hungry_philosophers(num_philosophers, hungry_count):
    hungry_philosophers = []
    for i in range(hungry_count):
        while True:
            pos = int(input(f"Enter position for hungry philosopher {i + 1} (0 to {num_philosophers - 1}): "))
            if 0 <= pos < num_philosophers and pos not in hungry_philosophers:
                hungry_philosophers.append(pos)
                break
            else:
                print("Invalid position or duplicate entry, try again.")
    return hungry_philosophers

def one_at_a_time(hungry_philosophers):
    for philosopher_id in hungry_philosophers:
        print(f"\nPhilosopher {philosopher_id + 1} is granted to eat.")
        time.sleep(random.uniform(1, 2))
        print(f"Philosopher {philosopher_id + 1} finished eating.")

def two_at_a_time(hungry_philosophers):
    granted_pairs = set()
    for i in range(len(hungry_philosophers)):
        for j in range(i + 1, len(hungry_philosophers)):
            if abs(hungry_philosophers[i] - hungry_philosophers[j]) > 1:
                granted_pairs.add((hungry_philosophers[i], hungry_philosophers[j]))
    for pair in granted_pairs:
        print(f"\nPhilosopher {pair[0] + 1} and Philosopher {pair[1] + 1} are granted to eat.")
        time.sleep(random.uniform(1, 2))
        print(f"Philosopher {pair[0] + 1} and Philosopher {pair[1] + 1} finished eating.")

def main_menu(hungry_philosophers):
    while True:
        print("\nMenu:")
        print("1. One can eat at a time")
        print("2. Two can eat at a time")
        print("3. Exit")
        choice = int(input("Enter your choice: "))
        if choice == 1:
            one_at_a_time(hungry_philosophers)
        elif choice == 2:
            two_at_a_time(hungry_philosophers)
        elif choice == 3:
            print("Exiting program.")
            break
        else:
            print("Invalid option, try again.")

def main():
    print("K057")
    num_philosophers = int(input("Enter the total number of philosophers: "))
    chopsticks = initialize_chopsticks(num_philosophers)
    hungry_count = int(input("How many philosophers are hungry: "))
    if hungry_count == num_philosophers:
        print("\nAll philosophers are hungry. Deadlock stage will occur.\nExiting...")
        return
    hungry_philosophers = get_hungry_philosophers(num_philosophers, hungry_count)
    main_menu(hungry_philosophers)

if __name__ == "__main__":
    main()
```

### Output:

```
K057, Bruh
Enter the total number of philosophers: 5
How many philosophers are hungry: 3
Enter position for hungry philosopher 1 (0 to 4): 2
Enter position for hungry philosopher 2 (0 to 4): 4
Enter position for hungry philosopher 3 (0 to 4): 3

Menu:
1. One can eat at a time
2. Two can eat at a time
3. Exit
Enter your choice: 1

Philosopher 3 is granted to eat.
Philosopher 3 finished eating.
Philosopher 5 is granted to eat.
Philosopher 5 finished eating.
Philosopher 4 is granted to eat.
Philosopher 4 finished eating.

Menu:
1. One can eat at a time
2. Two can eat at a time
3. Exit
Enter your choice: 3
Exiting program.
```

