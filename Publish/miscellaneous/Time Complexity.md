---
Title: Time Complexity
Status: 
marker: 
tags: 
Date: 2024.10.19
Time: 13:42
---
# Time Complexity Comparison: O(log(n)) vs O(n)

## O(log(n)) - Logarithmic Time Complexity
- **Definition**: The time it takes to run the algorithm increases logarithmically as the input size grows. 
- **Example Algorithm**: Binary search, where the search space is halved at each step.
- **Performance**: Extremely efficient for large inputs since it reduces the problem size exponentially.
- **Graph Characteristics**: Starts fast and slows down as input size increases, but the growth rate is slow.

### Growth Example:
| Input Size (n) | O(log(n)) Steps (Base 2) | O(n) Steps |
| -------------- | ------------------------ | ---------- |
| 1              | 0                        | 1          |
| 10             | 3                        | 10         |
| 100            | 7                        | 100        |
| 1,000          | 10                       | 1,000      |
| 10,000         | 14                       | 10,000     |
| 100,000        | 17                       | 100,000    |
| 1,000,000      | 20                       | 1,000,000  |

---

## O(n) - Linear Time Complexity
- **Definition**: The time it takes to run the algorithm increases linearly as the input size grows.
- **Example Algorithm**: Linear search, where every element is checked one by one.
- **Performance**: Less efficient than O(log(n)) for large inputs because it scales directly with the input size.
- **Graph Characteristics**: Increases steadily with the input size.

### Growth Example:
| Input Size (n) | O(n) Steps |
| -------------- | ---------- |
| 1              | 1          |
| 10             | 10         |
| 100            | 100        |
| 1,000          | 1,000      |
| 10,000         | 10,000     |
| 100,000        | 100,000    |
| 1,000,000      | 1,000,000  |

---

## Visualizing the Growth Rates

- O(log(n)) grows very slowly, even for large values of `n`, making it much more scalable.
- O(n) grows linearly with input size, making it less efficient as the input size increases.




# References


###### Information
- date: 2024.10.19
- time: 13:42