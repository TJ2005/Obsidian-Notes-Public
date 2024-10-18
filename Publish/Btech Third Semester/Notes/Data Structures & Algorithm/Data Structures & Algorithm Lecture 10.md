---
Title: Data Structures & Algorithm Lecture 10
Status: 
marker:
  - "[[Linked List]]"
  - "[[Algorithm]]"
tags:
  - BTech
Date: 2024.08.28
Time: 14:09
---
### Structure of a Linked List

1. **Node**: The basic unit of a linked list. Each node contains:
   - **Data**: The value or information stored in the node.
   - **Next**: A reference (or pointer) to the next node in the list. In a singly linked list, this is a single pointer. In a doubly linked list, there is an additional pointer to the previous node.

2. **Head**: The starting node of the linked list. It serves as the entry point to access the list. If the list is empty, the head is typically set to `null` (or `nullptr` in C++).

### Types of Linked Lists

1. **Singly Linked List**:
   - Each node has a single link to the next node.
   - Example structure: `Head -> Node1 -> Node2 -> Node3 -> NULL`
   - **Advantages**: Simple implementation, efficient insertion and deletion at the beginning of the list.w
   - **Disadvantages**: Traversal is only possible in one direction (forward).

2. **Doubly Linked List**:
   - Each node has two links: one to the next node and one to the previous node.
   - Example structure: `Head <-> Node1 <-> Node2 <-> Node3 <-> NULL`
   - **Advantages**: Allows traversal in both directions (forward and backward).
   - **Disadvantages**: More complex implementation and requires extra memory for the additional link.

3. **Circular Linked List**:
   - The last node in the list points back to the first node, forming a circle.
   - Can be singly or doubly linked.
   - Example structure for singly circular linked list: `Head -> Node1 -> Node2 -> Node3 -> Head`
   - **Advantages**: Useful for applications that need a circular traversal of nodes (e.g., round-robin scheduling).
   - **Disadvantages**: Can be complex to handle edge cases and needs special logic to detect the end of the list.

### Operations on Linked Lists

1. **Insertion**:
   - At the beginning: Insert a new node before the current head.
   - At the end: Traverse the list to find the last node and insert the new node after it.
   - At a specific position: Traverse the list to the desired position and insert the new node.

2. **Deletion**:
   - From the beginning: Remove the head node and update the head to the next node.
   - From the end: Traverse the list to find the second-to-last node and update its `next` pointer to `null`.
   - From a specific position: Traverse to the desired position, update the pointers to bypass the node to be deleted.

3. **Traversal**:
   - Iterate through the list from the head to the end, accessing each node's data.

4. **Search**:
   - Traverse the list to find a node with a specific value or condition.

### Advantages of Linked Lists

- **Dynamic Size**: Can grow or shrink as needed, without the need for preallocating space.
- **Efficient Insertion/Deletion**: Inserting or deleting nodes is more efficient compared to arrays, especially if operations are performed at the beginning or in the middle of the list.

### Disadvantages of Linked Lists

- **Memory Overhead**: Requires extra memory for storing pointers.
- **Sequential Access**: Accessing elements requires traversal from the head, which can be slower compared to direct indexing in arrays.

### Example in C

Here’s a basic example of a singly linked list in C:

```c
#include <stdio.h>
#include <stdlib.h>

// Node structure 
typedef struct Node {
    int data;
    struct Node *next;
} Node;

// Function to create a new node
Node* createNode(int value) {
    Node *newNode = (Node*)malloc(sizeof(Node));
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}

// Function to print the linked list
void printList(Node *head) {
    Node *temp = head;
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    // Create nodes
    Node *head = createNode(1);
    head->next = createNode(2);
    head->next->next = createNode(3);

    // Print the list
    printList(head);

    return 0;
}
```

A linked list is a fundamental data structure used in computer science to organize and store a collection of elements. Unlike arrays, linked lists do not store elements in contiguous memory locations. Instead, each element, called a node, contains a reference (or link) to the next node in the sequence. Here’s a detailed breakdown of linked lists:

### Structure of a Linked List

1. **Node**: The basic unit of a linked list. Each node contains:
   - **Data**: The value or information stored in the node.
   - **Next**: A reference (or pointer) to the next node in the list. In a singly linked list, this is a single pointer. In a doubly linked list, there is an additional pointer to the previous node.

2. **Head**: The starting node of the linked list. It serves as the entry point to access the list. If the list is empty, the head is typically set to `null` (or `nullptr` in C++).

### Types of Linked Lists

1. **Singly Linked List**:
   - Each node has a single link to the next node.
   - Example structure: `Head -> Node1 -> Node2 -> Node3 -> NULL`
   - **Advantages**: Simple implementation, efficient insertion and deletion at the beginning of the list.
   - **Disadvantages**: Traversal is only possible in one direction (forward).

2. **Doubly Linked List**:
   - Each node has two links: one to the next node and one to the previous node.
   - Example structure: `Head <-> Node1 <-> Node2 <-> Node3 <-> NULL`
   - **Advantages**: Allows traversal in both directions (forward and backward).
   - **Disadvantages**: More complex implementation and requires extra memory for the additional link.

3. **Circular Linked List**:
   - The last node in the list points back to the first node, forming a circle.
   - Can be singly or doubly linked.
   - Example structure for singly circular linked list: `Head -> Node1 -> Node2 -> Node3 -> Head`
   - **Advantages**: Useful for applications that need a circular traversal of nodes (e.g., round-robin scheduling).
   - **Disadvantages**: Can be complex to handle edge cases and needs special logic to detect the end of the list.

### Operations on Linked Lists

1. **Insertion**:
   - At the beginning: Insert a new node before the current head.
   - At the end: Traverse the list to find the last node and insert the new node after it.
   - At a specific position: Traverse the list to the desired position and insert the new node.

2. **Deletion**:
   - From the beginning: Remove the head node and update the head to the next node.
   - From the end: Traverse the list to find the second-to-last node and update its `next` pointer to `null`.
   - From a specific position: Traverse to the desired position, update the pointers to bypass the node to be deleted.

3. **Traversal**:
   - Iterate through the list from the head to the end, accessing each node's data.

4. **Search**:
   - Traverse the list to find a node with a specific value or condition.

### Advantages of Linked Lists

- **Dynamic Size**: Can grow or shrink as needed, without the need for preallocating space.
- **Efficient Insertion/Deletion**: Inserting or deleting nodes is more efficient compared to arrays, especially if operations are performed at the beginning or in the middle of the list.

### Disadvantages of Linked Lists

- **Memory Overhead**: Requires extra memory for storing pointers.
- **Sequential Access**: Accessing elements requires traversal from the head, which can be slower compared to direct indexing in arrays.

### Example in C

Here’s a basic example of a singly linked list in C:

```c
#include <stdio.h>
#include <stdlib.h>

// Node structure 
typedef struct Node {
    int data;
    struct Node *next;
} Node;

// Function to create a new node
Node* createNode(int value) {
    Node *newNode = (Node*)malloc(sizeof(Node));
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}

// Function to print the linked list
void printList(Node *head) {
    Node *temp = head;
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    // Create nodes
    Node *head = createNode(1);
    head->next = createNode(2);
    head->next->next = createNode(3);

    // Print the list
    printList(head);

    return 0;
}
```

In this example, `createNode` creates a new node with the given data, and `printList` traverses and prints the linked list.

Here's a revised note based on your provided code and explanation:

---

### Algorithm for Insertion in a Linked List at Head

1. **Create a New Node Dynamically**:
   - Allocate memory for the new node using `malloc`.
   - Example: `var = (struct node*)malloc(sizeof(struct node));`

2. **Set the Data for the New Node**:
   - Assign the value to the `data` field of the new node.
   - Example: `var->data = value;`

3. **Link the New Node to the Existing List**:
   - Set the `next` pointer of the new node to point to the current `HEAD`.
   - Example: `var->next = head;`

4. **Update the Head Pointer**:
   - Set `HEAD` to point to the new node, making it the first node in the list.
   - Example: `head = var;`

### Code Example

```cpp
struct node* var;

// Step 1: Allocate memory for the new node
var = (struct node*)malloc(sizeof(struct node));

// Step 2: Set the data for the new node
var->data = value;

// Step 3: Link the new node to the existing list
var->next = head;

// Step 4: Update the head pointer
head = var;
```

### Explanation
- **Self-Referencing on First Element**: When inserting the first element, `head` is initially `NULL`. The algorithm correctly handles this by setting the `next` pointer of the new node to `NULL`, making the new node the first and only node in the list.
- This process ensures that the new node is always added at the beginning of the list, making it the new head. This approach works correctly even when the list is initially empty.

---

### Linked List Insertion at tail
There is only a pointer towards the header first.

```cpp
struct node* var;


//step 1: Allocate memory for the new node to be attached at the end
var = (struct node*)malloc(sizeof(struct node))
//step 2: add value to the next new node
var->data=value;
//step3:
temp = head;
if(head==NULL){

	head=var;
	head->next=null;
}
else
{
	while(temp->next!=NULL){
		temp= temp->next;
	}
	var->next=NULL;
	
	temp->next=var;
}

```

```cpp
while(temp->next!=NULL)
{
	temp=temp->
}
```
# References


###### Information
- date: 2024.08.28
- time: 14:09