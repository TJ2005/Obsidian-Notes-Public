---
Title: Data Structures & Algorithm Lecture 18
Status: 
marker: 
tags: 
Date: 2024.09.25
Time: 14:10
---
Continued from [[Data Structures & Algorithm Lecture 17]]
### Data Structures & Algorithm - Lecture 18

#### **Running Time of Merge Sort**
- **Time Complexity:**  
  Merge sort divides the input array into two halves, recursively sorts them, and then merges the two sorted halves.
  
  - **Best Case:** O(n log n)
  - **Average Case:** O(n log n)
  - **Worst Case:** O(n log n)

  This complexity is derived from the fact that the array is repeatedly divided into two halves (log n divisions) and each level takes linear time O(n) to merge the halves.

#### **Merge Sort: Step-by-Step**
1. **Divide:** The list is divided into two equal halves.
2. **Conquer:** Recursively sort each half.
3. **Merge:** Merge the two sorted halves to form a sorted list.

- **Space Complexity:** O(n)  
  Merge sort requires additional space for temporary arrays during the merge process.

#### **Binary Search**
- Binary search is a technique used to find an element in a **sorted array**.
- **Time Complexity:** O(log n) for all cases.
- **Steps Involved:**
  1. Compare the target value to the middle element.
  2. If the target equals the middle element, return the index.
  3. If the target is smaller than the middle element, repeat the search in the left half.
  4. If the target is larger, repeat in the right half.

#### **Other Sorting Techniques**
1. **Bubble Sort:**
   - **Best Case:** O(n) (Already sorted)
   - **Average Case:** O(n²)
   - **Worst Case:** O(n²)
   - Repeatedly swaps adjacent elements if they are in the wrong order.
   
2. **Insertion Sort:**
   - **Best Case:** O(n)
   - **Average Case:** O(n²)
   - **Worst Case:** O(n²)
   - Builds the sorted array one element at a time by inserting each element into its correct position.

3. **Selection Sort:**
   - **Best Case, Average Case, Worst Case:** O(n²)
   - Divides the array into sorted and unsorted parts, repeatedly selecting the smallest element from the unsorted part and moving it to the sorted part.

4. **Quick Sort:**
   - **Best Case:** O(n log n)
   - **Average Case:** O(n log n)
   - **Worst Case:** O(n²) (when the pivot is the smallest or largest element every time)
   - Uses a pivot element to partition the array, then recursively sorts the partitions.

#### **Number of Iterations in Sorting Techniques**
- **Bubble Sort:** Each pass compares adjacent elements, with each pass reducing the number of comparisons by 1. It may take up to **n-1 passes** in the worst case.
  
- **Insertion Sort:** In the worst case, each element is compared with all previous elements, leading to **n-1 iterations** for the outer loop, with an inner loop making comparisons.

- **Selection Sort:** The outer loop iterates **n-1 times** (as it repeatedly finds the minimum element).

- **Merge Sort:** Logarithmic in terms of the depth of recursion (log n levels of recursion) and linear merging process at each level, resulting in **n log n iterations** in total.

- **Quick Sort:** The number of iterations depends on the pivot selection, with worst-case recursion depth of **n**, but on average, it performs **n log n iterations**. 

---

#### **References:**
1. Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). *Introduction to Algorithms* (3rd ed.). MIT Press.
2. Weiss, M. A. (2011). *Data Structures and Algorithm Analysis in C++* (4th ed.). Pearson.](<# Data Structures & Algorithm Lecture 18

### **Hashing: Why Do We Need It?**

#### **What is Hashing?**
Hashing is a process of mapping large datasets into smaller, fixed-size values called "hashes" using a hash function. The primary goal of hashing is to enable fast data retrieval, making it efficient to search, insert, and delete elements.

A **hash function** takes input (of any length) and returns an output (hash code) of a fixed size. This hash code represents the input data in a way that is computationally easy to generate but difficult to reverse.

#### **Why Do We Need Hashing?**
1. **Efficient Data Retrieval:**
   Hashing allows constant time complexity **O(1)** for average-case search, insertion, and deletion in hash tables. This is significantly faster than searching through arrays or linked lists, which would take linear time **O(n)**.
   
2. **Optimized Data Storage:**
   Hashing is used to store data in such a way that it minimizes the time taken to access the data. Data is stored in a hash table, and each data entry is mapped to an index in the table using the hash function.

3. **Collision Handling:**
   In hashing, multiple inputs can result in the same hash value, which is called a "collision." Efficient hashing algorithms include mechanisms like chaining and open addressing to handle collisions, ensuring that data is still stored and retrieved efficiently.

4. **Applications in Real Life:**
   - **Databases:** Hashing is commonly used in database indexing, where large datasets can be quickly searched based on hash codes.
   - **Cryptography:** Hash functions are fundamental in cryptography, ensuring data integrity and security.
   - **File Systems:** File systems use hashing to speed up the process of finding files and folders based on their names.
   - **Caching:** Web browsers and servers use hashing to cache resources, ensuring that previously accessed content is quickly retrieved.

#### **Advantages of Hashing:**
- **Speed:** Hashing provides near-instant access to data with time complexity of O(1) in many cases, making it ideal for large datasets.
- **Simplicity:** Data structures like hash tables are straightforward to implement and offer an efficient solution to many problems.
- **Memory Efficiency:** Hashing often uses a smaller amount of memory by distributing data across a table without needing to store every element in sequence.

#### **When Do We Use Hashing?**
- **Large Datasets:** When working with large amounts of data that need to be searched quickly, hashing is a crucial technique.
- **Frequent Lookups:** If your application requires frequent lookups, such as in caching, database indexing, or searching in dictionaries, hashing can drastically improve performance.
- **Preventing Duplicates:** Hashing is often used to avoid duplicates in data storage systems by comparing hash values rather than entire datasets.

#### **Drawbacks of Hashing:**
- **Collisions:** While hashing is efficient, collisions are inevitable. Effective collision-handling strategies are necessary to maintain performance.
- **Space Overhead:** A well-designed hash table may require more space than an array due to unused slots.
- **Not Ordered:** Unlike trees, hash tables do not maintain any inherent order of data, so they are not suitable when order matters.
#### **Conclusion**
Hashing is essential for modern computing, especially when dealing with large datasets where efficient data retrieval and management are critical. It provides an optimal solution for fast lookups and data access, playing a key role in various fields, from databases to cryptography.

### **Example of Hashing Using Modulo 10 (Mod 10)**

#### **Hash Function: Modulo Operation**
A simple hash function can be defined as:
\[ \text{hash(key)} = \text{key} \mod 10 \]

This function divides the key by 10 and returns the remainder. The remainder serves as the index where the data will be stored in the hash table.

#### **Example:**
Let’s take a hash table of size 10 (with indices from 0 to 9) and use the hash function \(\text{key} \mod 10\) to determine where keys will be placed.

- Keys to insert: **23, 35, 49, 61, 72, 85**
  
- Applying the hash function:
  - For key **23**, \[ 23 \mod 10 = 3 \]. So, **23** is stored at index 3.
  - For key **35**, \[ 35 \mod 10 = 5 \]. So, **35** is stored at index 5.
  - For key **49**, \[ 49 \mod 10 = 9 \]. So, **49** is stored at index 9.
  - For key **61**, \[ 61 \mod 10 = 1 \]. So, **61** is stored at index 1.
  - For key **72**, \[ 72 \mod 10 = 2 \]. So, **72** is stored at index 2.
  - For key **85**, \[ 85 \mod 10 = 5 \]. So, **85** is stored at index 5 (collision with key **35**).

#### **Resulting Hash Table:**

| Index | Value  |
|-------|--------|
| 0     |        |
| 1     | 61     |
| 2     | 72     |
| 3     | 23     |
| 4     |        |
| 5     | 35, 85 |
| 6     |        |
| 7     |        |
| 8     |        |
| 9     | 49     |

#### **Collision:**
In the example above, a collision occurs at index 5 for keys **35** and **85**, since both hash to the same value.

#### **Drawbacks of Using Mod 10:**

1. **Limited Range of Indices (Hash Table Size):**
   - The `mod 10` function will always produce hash values between 0 and 9, limiting the possible positions where keys can be stored. This can quickly lead to collisions, especially if the dataset contains many keys.
   - **Case Example:** Inserting keys **25, 35, 45, 55, 65** would all result in the same index (`mod 10` results in 5), causing multiple collisions.

2. **High Collision Rate:**
   - The modulo operation can result in a high number of collisions, especially if the input dataset contains keys with similar values. This leads to poor performance as the number of collisions grows.
   - **Case Example:** Inserting keys **10, 20, 30, 40, 50** will all hash to index 0 (`mod 10` result is 0), resulting in collisions for every key.

3. **Poor Distribution:**
   - Simple hash functions like `mod 10` often lead to poor distribution of keys across the hash table. Some indices may end up with too many keys (collisions), while others may remain empty, resulting in inefficient space usage.
   - **Case Example:** If we insert a series of keys like **101, 102, 103, 104**, they all map to different indices, but if we insert numbers like **100, 110, 120, 130**, they all hash to index 0, leading to uneven distribution.

4. **Not Suitable for Large Data Sets:**
   - For larger datasets or keys, a small hash function like `mod 10` is insufficient because it cannot handle the vast number of keys without excessive collisions. A more sophisticated hash function would be needed to reduce collisions and improve efficiency.
   - **Case Example:** If we have 1000 keys and use `mod 10`, we would only have 10 possible hash values (from 0 to 9), meaning that 100 keys would hash to the same index on average, severely impacting performance.

#### **Collision Handling Techniques:**
To overcome these drawbacks, collision handling mechanisms are often used:
1. **Chaining:** In each index of the hash table, we store a linked list or another structure to hold multiple values.
   - For example, in the previous case, at index 5, we store both **35** and **85** in a linked list.
   
2. **Open Addressing:** Instead of storing the collided value at the same index, we search for the next available position in the table.

#### **Conclusion:**
While the `mod 10` hash function is simple and easy to implement, it can lead to significant performance issues due to high collision rates and poor key distribution, especially with large datasets. More advanced hash functions or collision handling strategies are needed to ensure efficient hashing in practical applications.


### **Collision Resolution Using Clusters: Linear Probing**

**Linear probing** is a technique used in open addressing to resolve collisions in a hash table. When a collision occurs (i.e., two keys map to the same index), linear probing searches for the next available slot by moving sequentially (one step at a time) through the hash table until it finds an empty slot.

#### **Hash Function Example:**
Using the hash function \( h(k) = k \mod 10 \) to insert the keys **7, 18, 19, 94, 7, 19** into a hash table of size 10:

1. **Insert 7:**  
   \( h(7) = 7 \mod 10 = 7 \)  
   The index 7 is empty, so **7** is inserted at index 7.
   
2. **Insert 18:**  
   \( h(18) = 18 \mod 10 = 8 \)  
   The index 8 is empty, so **18** is inserted at index 8.
   
3. **Insert 19:**  
   \( h(19) = 19 \mod 10 = 9 \)  
   The index 9 is empty, so **19** is inserted at index 9.

4. **Insert 94:**  
   \( h(94) = 94 \mod 10 = 4 \)  
   The index 4 is empty, so **94** is inserted at index 4.

5. **Insert 7 (again):**  
   \( h(7) = 7 \mod 10 = 7 \)  
   The index 7 is already occupied by the first **7**.  
   Linear probing checks the next index (index 8), but it is occupied by **18**.  
   It then checks index 9, but that is occupied by **19**.  
   Next, it checks index 0, which is empty. So, **7** is inserted at index 0.

6. **Insert 19 (again):**  
   \( h(19) = 19 \mod 10 = 9 \)  
   Index 9 is occupied by the first **19**.  
   Linear probing checks the next index (index 0), but it is occupied by **7**.  
   It then checks index 1, which is empty. So, **19** is inserted at index 1.

#### **Resulting Hash Table:**

| Index | Value |
|-------|-------|
| 0     | 7     |
| 1     | 19    |
| 2     |       |
| 3     |       |
| 4     | 94    |
| 5     |       |
| 6     |       |
| 7     | 7     |
| 8     | 18    |
| 9     | 19    |

#### **Explanation of Linear Probing:**
- When a collision occurs, linear probing finds the next available slot by searching sequentially (in a linear manner) through the hash table.
- For example, when inserting the second **7**, a collision occurs at index 7. Linear probing then checks subsequent slots (8, 9, and finally 0) until it finds an available spot at index 0.

#### **Advantages of Linear Probing:**
1. **Simple to implement:** Linear probing is a straightforward method for resolving collisions.
2. **No additional memory:** All elements are stored within the hash table itself, so no extra structures like linked lists are needed.

#### **Drawbacks of Linear Probing:**
1. **Primary Clustering:** Linear probing can lead to **primary clustering**, where a cluster of filled slots forms, and new collisions lead to increasingly longer probing sequences. This makes future insertions slower, as more indices need to be checked before finding an empty slot.
   - In the example, once the second **7** collided, linear probing had to check several indices (7, 8, and 9) before finding an empty slot.
   
2. **Performance Degradation:** As clusters grow larger, the time required to find an empty slot increases, which degrades performance for both insertion and search operations.

#### **Conclusion:**
Linear probing is an efficient and simple technique for resolving collisions in hash tables. However, as the number of collisions increases, primary clustering can significantly slow down performance, especially when the hash table becomes crowded. To mitigate this, other methods like **quadratic probing** or **double hashing** can be used to reduce clustering effects.


---

#### **References:**
1. Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). *Introduction to Algorithms* (3rd ed.). MIT Press.
2. Weiss, M. A. (2011). *Data Structures and Algorithm Analysis in C++* (4th ed.). Pearson.](<# Running time of merge sort
time complexity for all the cases is n.log(n)>)
# References


###### Information
- date: 2024.09.25
- time: 14:10
- Continued from [[Data Structures & Algorithm Lecture 20]]