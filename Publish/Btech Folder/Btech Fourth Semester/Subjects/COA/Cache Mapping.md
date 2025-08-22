---
Title: Cache Mapping
Status: true
marker:
  - "[[Computer Organization and Architecture (COA)]]"
tags:
  - Note
  - BTech
  - self-study
Date: 2025.03.05
Time: 09:32
---
This note covers my own study of what mapping of cache is
# Cache Mapping Types

In computer architecture, cache mapping is a crucial concept that determines how data from the main memory is stored and accessed in the cache memory. Understanding cache mapping is essential for optimizing system performance. Here's a detailed explanation of the different types of cache mapping techniques, their attributes, and their significance.

## Attributes of Cache Mapping
You will need to understand the following attributes to grasp the concept of cache mapping:

1. **Tag**:
   - The tag is a part of the memory address used to identify which memory block is stored in a cache line. It helps in determining if the data in the cache is the same as the requested data.
1. **Index**:
   - The index specifies the cache line where a memory block can be placed. It is used to locate the specific cache line within the cache.
1. **Offset (Block Offset)**:
   - The offset indicates the specific word or byte within a block. It is used to access data within the block once it is loaded into the cache.
1. **Set**:
   - In set-associative caches, the cache is divided into sets, each containing a fixed number of lines (ways). The set index determines which set a memory block maps to.
1. **Way**:
   - In set-associative caches, each set contains multiple lines (ways). The way determines the specific line within a set where the block is stored.

## Types of Cache Mapping

### 1. Direct Mapped Cache
- **Description**: Each memory block is mapped to exactly one cache line.
- **Structure**: The address is divided into tag, index, and offset fields.
- **Why It Matters**: Simple and fast due to straightforward mapping, but can suffer from high collision rates.

### 2. Fully Associative Cache
- **Description**: Any memory block can be loaded into any cache line.
- **Structure**: The address is divided into tag and offset fields; there is no index field.
- **Why It Matters**: Flexible and reduces collisions, but more complex and slower due to the need to search all cache lines.

### 3. Set Associative Cache
- **Description**: Combines aspects of direct-mapped and fully associative caches. The cache is divided into sets, and each set contains a fixed number of lines (ways).
- **Structure**: The address is divided into tag, set index, and offset fields.
- **Why It Matters**: Balances simplicity and flexibility, reducing collisions and improving performance compared to direct-mapped cache.

## Advantages and Disadvantages

| **Mapping Type**       | **Advantages**                                                                 | **Disadvantages**                                                                 |
|------------------------|-------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| Direct Mapped Cache    | - Simple and fast.<br>- Easy to implement.                                    | - High chance of collisions.<br>- Limited flexibility.                           |
| Fully Associative Cache| - Flexible placement of blocks.<br>- Reduces collisions.                      | - Complex and slower.<br>- Requires searching all cache lines.                   |
| Set Associative Cache  | - Balances simplicity and flexibility.<br>- Reduces collisions compared to direct-mapped.<br>- Improved performance. | - More complex than direct-mapped.<br>- Still has some collision potential.      |

## Summary of Cache Mapping Types

| **Attribute**          | **Direct Mapped Cache** | **Fully Associative Cache** | **Set Associative Cache** |
|------------------------|-------------------------|-----------------------------|---------------------------|
| **Mapping**            | One-to-one              | Any-to-any                  | Set-based                 |
| **Address Fields**     | Tag, Index, Offset      | Tag, Offset                | Tag, Set Index, Offset    |
| **Collision Rate**     | High                    | Low                        | Moderate                  |
| **Complexity**         | Low                     | High                       | Moderate                  |
| **Performance**        | Fast                    | Slower                     | Balanced                  |
To checkout the problems, visit [[Computer Organization and Architecture Lecture 13]].

# References


###### Information
- date: 2025.03.05
- time: 09:32