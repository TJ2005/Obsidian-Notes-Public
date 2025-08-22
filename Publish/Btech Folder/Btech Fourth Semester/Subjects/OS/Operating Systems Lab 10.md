---
Title: "Operating Systems Lab 10"
Status: 
marker: 
tags: 
Date: "2025.04.07"
Time: "08:37"
---
# Page Replacement Algorithm
The page replacement algorithm 
### Code
```python
# Page Replacement Algorithms in Python

def fifo(pages, frames):
    queue = []
    faults = 0
    for page in pages:
        if page not in queue:
            if len(queue) < frames:
                queue.append(page)
            else:
                queue.pop(0)
                queue.append(page)
            faults += 1
        print(f"Frames: {queue}")
    print(f"Total Page Faults (FIFO): {faults}")


def lru(pages, frames):
    queue = []
    faults = 0
    recently_used = {}

    for i, page in enumerate(pages):
        if page not in queue:
            if len(queue) < frames:
                queue.append(page)
            else:
                # Find the least recently used page
                lru_page = min(recently_used, key=recently_used.get)
                queue.remove(lru_page)
                queue.append(page)
            faults += 1
        recently_used[page] = i
        print(f"Frames: {queue}")
    print(f"Total Page Faults (LRU): {faults}")


def optimal(pages, frames):
    queue = []
    faults = 0

    for i in range(len(pages)):
        page = pages[i]
        if page not in queue:
            if len(queue) < frames:
                queue.append(page)
            else:
                # Find the page not used for the longest time in future
                future_uses = {}
                for q_page in queue:
                    if q_page in pages[i+1:]:
                        future_uses[q_page] = pages[i+1:].index(q_page)
                    else:
                        future_uses[q_page] = float('inf')
                to_remove = max(future_uses, key=future_uses.get)
                queue.remove(to_remove)
                queue.append(page)
            faults += 1
        print(f"Frames: {queue}")
    print(f"Total Page Faults (Optimal): {faults}")


# Example usage
if __name__ == "__main__":
    pages = list(map(int, input("Enter page reference string (space-separated): ").split()))
    frames = int(input("Enter number of frames: "))

    print("\n--- FIFO ---")
    fifo(pages, frames)

    print("\n--- LRU ---")
    lru(pages, frames)

    print("\n--- Optimal ---")
    optimal(pages, frames)

```

```bash
FIFO Page Replacement:
Frames: [7]
Frames: [7, 0]
Frames: [7, 0, 1]
Frames: [7, 0, 1, 2]
Frames: [0, 1, 2, 0]
Frames: [1, 2, 0, 3]
Frames: [2, 0, 3, 0]
Frames: [0, 3, 0, 4]
Frames: [3, 0, 4, 2]
Frames: [0, 4, 2, 3]
Frames: [4, 2, 3, 0]
Frames: [2, 3, 0, 3]
Frames: [3, 0, 3, 2]
Total Page Faults (FIFO): 9

LRU Page Replacement:
Frames: [7]
Frames: [7, 0]
Frames: [7, 0, 1]
Frames: [7, 0, 1, 2]
Frames: [7, 1, 2, 0]
Frames: [1, 2, 0, 3]
Frames: [2, 0, 3]
Frames: [2, 3, 0, 4]
Frames: [3, 0, 4, 2]
Frames: [0, 4, 2, 3]
Frames: [4, 2, 3, 0]
Frames: [4, 2, 0, 3]
Frames: [4, 0, 3, 2]
Total Page Faults (LRU): 10

Optimal Page Replacement:
Frames: [7]
Frames: [7, 0]
Frames: [7, 0, 1]
Frames: [7, 0, 1, 2]
Frames: [7, 1, 2, 0]
Frames: [1, 2, 0, 3]
Frames: [2, 0, 3]
Frames: [2, 0, 3, 4]
Frames: [0, 3, 4, 2]
Frames: [0, 4, 2, 3]
Frames: [4, 2, 3, 0]
Frames: [4, 2, 0, 3]
Frames: [4, 0, 3, 2]
Total Page Faults (Optimal): 9

```
# References


###### Information
- date: 2025.04.07
- time: 08:37