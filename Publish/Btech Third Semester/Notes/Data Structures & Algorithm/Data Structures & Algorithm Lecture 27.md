---
Title: Data Structures & Algorithm Lecture 15
Status: 
marker:
  - "[[Indirectional Operator]]"
  - "[[Pointers]]"
tags:
  - BTech
Date: 2024.09.14
Time: 12:28
---
Continued from [[Data Structures & Algorithm Lecture 14]]

---

# C++ Pointer and Node Management

## Indirectional Operator (`*`)

In C++, the indirectional operator (`*`) is used to declare a pointer and to dereference a pointer.

### Example:

```cpp
int *x;
```

- In this line of code, `int *x;` declares a pointer `x` that is expected to store the **address** of an integer variable.
- The operator `*` indicates that `x` is a pointer to an integer.
  
### Key Points:
- The indirectional operator does not store the value directly; instead, it **stores the address** of the variable that will hold an integer value.
- You can later use this pointer to **access or modify** the value of the integer stored at the memory address it points to by dereferencing it using `*`.

---

## Creating a Node and Assigning It as the Start

In linked lists or other dynamic data structures, creating and assigning nodes dynamically is a crucial operation.

### Example Code:

```cpp
Node* createNode(int data) {
    Node *newNode = (Node*)malloc(sizeof(Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}
```

### Explanation:
- **`Node* createNode(int data)`**: This function creates a new node that will store the given integer data.
- **`malloc(sizeof(Node))`**: Allocates the necessary memory space for the node.
- **`newNode->data = data`**: Assigns the data value to the node.
- **`newNode->next = NULL`**: Initializes the pointer to the next node as `NULL`, meaning it is the last node in the list for now.

### Steps Involved:
1. **Memory Allocation**: Using `malloc` to allocate memory for a new node.
2. **Assigning Data**: The data field in the node is assigned the value passed to the function.
3. **Next Pointer**: The `next` pointer is initialized to `NULL`, meaning it doesn't point to any other node yet.
4. **Return**: Returns the pointer to the newly created node.

---

## Malloc (`malloc`)

In C/C++, `malloc` is a function used to dynamically allocate memory at runtime.

### Important Notes:
- **No Initial Memory Allocation**: When `malloc` allocates memory, the allocated memory is not initialized; it may contain garbage values. You must explicitly assign values after allocation.
  
### Example:
```cpp
int *ptr = (int*)malloc(sizeof(int));
```
- This allocates memory for one integer and returns a pointer to the memory location.

- **Syntax**: `malloc(size_in_bytes)`
- **Returns**: A pointer to the beginning of the allocated memory block or `NULL` if the allocation fails.
  
**Note**: After using `malloc`, it is important to **free** the allocated memory to avoid memory leaks.

---


###### Information
- date: 2024.09.14
- time: 12:28
- Continued at [[Data Structures & Algorithm Lecture 16]]