---
Title: Data Structures & Algorithm Lecture 9
Status: 
marker: 
tags: 
Date: 2024.08.16
Time: 09:13
---
# Data Structures & Algorithm Lecture 9

#### Size of a circular queue
`(max+r-f)%`

# Priority Queue

#### Important Variables
- Min = Minimum element in the queue
- Max = Maximum element in the queue
- Key = The key of a value as in the dictionary
- Value = The value assigned to a key
### Concept
- Its a new ADT.
- Insert an Item
- Removes the best item
- Insertion happens first 
- Then the sorting happens

- A prioriity queue stores a collection of entry
	- Each Entry is a pair ( key, value )
	- Items are ordered with a key
- The position of the elements can be changed upon the arrival of a new element.
- Priority Queue is no longer a FIFO as insertions are governed by the priority.
- Void Insert
- Selection choose or select the min or max element
Consider a card from unsorted deck. Take it in your hand. Now you have 1 card in your hand. One card is always sorted. However when u get a new card you compare it with the other cards you already have on hand. If lesser card is ahead of those cards. If greater then put at the end. This same logic can be applied to understand shifting.

Consider {6,9,-2,-5,0}
1. *6,9*,-2,-5,0
2. *-2,6,9*,-5,0
3. *-5,-2,6,9*,0
4. *-5,-2,0,6,9*
It took n-1 passes to sort the queue.

#### Example Table
| Operation   | Output  | Priority Queue            |
| ----------- | ------- | ------------------------- |
| insert(5,A) | [(5,A)] | {(5,A)}                   |
| Insert(9,C) | [(9,C)] | {(5,A),(9,C)}             |
| Insert(3,B) | [(3,B)] | {(3,B),(5,A),(9,C)}       |
| Insert(7,D) | [(7,D)] | {(3,B),(5,A),(7,D),(9,C)} |
| min()       | e3      | {(3,B),(5,A),(7,D),(9,C)} |
| removeMin() | e3      | {(5,A),(7,D),(9,C)}       |
| size()      | 3       | {(5,A),(7,D),(9,C)}       |
| removeMin() | e1      | {(7,D),(9,C)}             |
| removeMin() | e4      | {(9,C)}                   |
| removeMin() | e2      | {}                        |
| removeMin() | "error" | {}                        |
| isEmpty()   | true    | {}                        |

# Applications of Priority Queue


# Format for m1
Question 1 : 2 question (2m) no options
Question 2 : 3 questions (3m) options

# Questions for m1
Exam Content
## Data Structures

### Classification

- Linear
- Non-Linear

### Array

- **1D Array**
    - Definition
    - Initialization
    - Operations (Insert, Delete, Traverse)
    - Refer First Lab
- **2D Array**
    - Definition
    - Initialization
    - Operations (Insert, Delete, Traverse)

### Stack

- Definition
    - Abstract Data Type (ADT)
    - Operations (PUSH, POP, PEEK, ISEMPTY, SIZE)
    - Applications
        - Decimal to Binary Conversion
        - Parentheses Matching
        - Reversing an Array
        - Binary to Decimal Conversion
        - Infix to Postfix/Prefix Conversion
        - Expression Evaluation

### Queue

- Definition
    - ADT
    - Types (Linear, Circular, Priority)
    - Applications of Different Queue Types

What is a primary queue
Different types of queue

# Unit 2
### Syllabus Content
- Introduction to linked list
- Rep of linked list in memory
- Singly Linked list and its operation
- Introduction to doubly linked list
- Linked list representation of stack and queues
- Applications

## Linked List
A linked list is a **linear data structure** of self referential objects where elements are stored in nodes, with each node containing a reference (or link) to the next node in the sequence. This structure allows for efficient insertions and deletions compared to arrays, which can be more cumbersome due to fixed sizes and shifting elements.
- Linear
- Self Referential
- Node
- First and Last Node (Null)
- Dummy Nodes
- Head and Tails Node

- Advantage
	- Dynamic
	- Non Contigous
	

### Things to remember
\* -> indirection pointer
& -> AddressOF

### Representation of Linked Lists in Memory

In memory, a linked list is represented as a collection of nodes. Each node typically consists of:

1. **Data**: The value or information stored in the node.
2. **Pointer/Reference**: An address pointing to the next node in the sequence.

#### Visual Representation

For a singly linked list:

- Each node has a reference to the next node.
- The last node’s reference is `null`, indicating the end of the list.

For a doubly linked list:

- Each node has two references: one to the next node and one to the previous node.
- The first node's previous reference and the last node's next reference are `null`.
### Nodes?
Storing addresses
### Single Linked List
One node.
- **Definition**: A singly linked list is a type of linked list where each node contains a single reference to the next node.
- **Operations**: Includes insertion, deletion, and traversal.
    - **Insertion**: Adding nodes at the beginning, end, or a specific position.
    - **Deletion**: Removing nodes from the list.
    - **Traversal**: Visiting each node starting from the head and continuing until the end of the list.
### Traversal in Single Linked list
Terminator is null
![[Single Linked List.excalidraw]]
Head is the first node.

### Double Linked List
- **Definition**: A doubly linked list is a linked list where each node has two references:
    - One pointing to the next node.
    - One pointing to the previous node.
- **Advantages**: Allows traversal in both forward and backward directions.
- **Operations**: Similar to a singly linked list but with additional operations for handling the previous references.
![[Double Linked List.excalidraw]]

## Why Linked Lists?
### Efficiency
When deletion happens it happens literally. It kills that data.
When Insertion happens we can just change the node address.

## Array v/s Linked Lists
- Arrays are suitable for
	- Inserting Deleting at the end
	- Random Accessing of any element
	- Searching the list for a particular value.
- Linked Lists are Suitable for
	- Inserting an element
	- Deleting an element
	- Applications where sequential access is required.
	- In situations where the numbers of elements cannot be be predicted before hand



# References


###### Information
- date: 2024.08.16
- time: 09:13