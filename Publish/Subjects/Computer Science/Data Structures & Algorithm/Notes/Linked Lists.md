---
Title: Linked Lists
Status: true
marker:
  - "[[Data Structures]]"
tags:
Date: 2025.08.21
Time: 19:12
---
# Linked Lists

# Main note
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
   - From a specific position: Traverse to the desired position, update the pointers to bypass the node to be deleted.w

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

Continued From [[Data Structures & Algorithm Lecture 10]]
### Complete Basic Structure
```cpp
#include <stdio.h>
#include <stdlib.h>
#include <iostream>
using namespace std;

struct node {
    int data;
    struct node* next;
};
```

### Insertion After an Element
```cpp
void insert_after(struct node* head, int to_check, int new_value) {
    struct node* var = head;
    
    while (var != NULL && var->data != to_check) {
        var = var->next;
    }
    
    if (var != NULL) {
        struct node* new_node = (struct node*)malloc(sizeof(struct node));
        new_node->data = new_value;
        new_node->next = var->next;
        var->next = new_node;
    } else {
        cout << "Element " << to_check << " not found.\n";
    }
}
```

### Insertion Before an Element
```cpp
#include <iostream>
#include <cstdlib>

struct node {
    int data;
    struct node* next;
};

void insert_before(struct node** head, int to_check, int new_value) {
    struct node* var = *head;
    struct node* prev = nullptr;
    
    // Step 1: Traverse the list to find the node with 'to_check' value
    while (var != nullptr && var->data != to_check) {
        prev = var;
        var = var->next;
    }
    
    // Step 2: If the node with 'to_check' value is found
    if (var != nullptr) {
        // Step 3: Create a new node with 'new_value'
        struct node* new_node = (struct node*)malloc(sizeof(struct node));
        new_node->data = new_value;
        new_node->next = var;
        
        // Step 4: If the element is at the head, update head
        if (prev == nullptr) {
            *head = new_node;  // Insert at the beginning
        } else {
            // Step 5: Otherwise, link the previous node to the new node
            prev->next = new_node;
        }
    } else {
        // Step 6: If the element 'to_check' is not found
        std::cout << "Element " << to_check << " not found.\n";
    }
}

```

### Insertion at the Head
```cpp
void insert_at_head(struct node** head, int new_value) {
    struct node* new_node = (struct node*)malloc(sizeof(struct node));
    new_node->data = new_value;
    new_node->next = *head;
    *head = new_node;
}
```

### Insertion at the End
```cpp
void insert_at_end(struct node* head, int new_value) {
    struct node* var = head;
    
    while (var->next != NULL) {
        var = var->next;
    }
    
    struct node* new_node = (struct node*)malloc(sizeof(struct node));
    new_node->data = new_value;
    new_node->next = NULL;
    var->next = new_node;
}
```

### Insertion Between Two Nodes
```cpp
void insert_between(struct node* head, int to_check, int new_value) {
    struct node* var = head;
    
    while (var != NULL && var->data != to_check) {
        var = var->next;
    }
    
    if (var != NULL && var->next != NULL) {
        struct node* new_node = (struct node*)malloc(sizeof(struct node));
        new_node->data = new_value;
        new_node->next = var->next;
        var->next = new_node;
    } else {
        cout << "Element " << to_check << " not found or has no next node.\n";
    }
}
```

### Deletion at the End
```cpp
int delete_end(struct node* head) {
    if (head == NULL) {
        cout << "UNDERFLOW\n";
        return 1;
    }
    
    struct node* var = head;
    struct node* prev = NULL;
    
    while (var->next != NULL) {
        prev = var;
        var = var->next;
    }
    
    if (prev == NULL) {
        free(head);
        head = NULL;
    } else {
        prev->next = NULL;
        free(var);
    }
    return 0;
}
```

### Deletion at the Head
```cpp
int delete_head(struct node** head) {
    if (*head == NULL) {
        cout << "UNDERFLOW\n";
        return 1;
    }
    
    struct node* temp = *head;
    *head = (*head)->next;
    free(temp);
    return 0;
}
```

### Deletion in the Middle
```cpp
int delete_mid(struct node* head, int to_check) {
    if (head == NULL || head->next == NULL) {
        cout << "UNDERFLOW or not enough nodes\n";
        return 1;
    }
    
    struct node* var = head;
    struct node* prev = NULL;
    
    while (var != NULL && var->data != to_check) {
        prev = var;
        var = var->next;
    }
    
    if (var == NULL) {
        cout << "Element " << to_check << " not found\n";
        return 1;
    }
    
    prev->next = var->next;
    free(var);
    return 0;
}
```

### Display Function
```cpp
void display(struct node* head) {
    if (head == NULL) {
        cout << "List is empty\n";
        return;
    }
    
    struct node* temp = head;
    while (temp != NULL) {
        cout << temp->data << " -> ";
        temp = temp->next;
    }
    cout << "NULL\n";
}
```

### Example Usage
```cpp
int main() {
    struct node* head = NULL;

    // Insert elements
    insert_at_head(&head, 10);
    insert_at_end(head, 30);
    insert_after(head, 10, 20);
    insert_between(head, 20, 25);
    insert_before(&head, 10, 5);

    // Display the list
    display(head);

    // Delete elements
    delete_end(head);
    delete_mid(head, 20);
    delete_head(&head);

    // Display the list again
    display(head);

    return 0;
}
```

This code handles all the linked list operations you mentioned, providing a comprehensive set of functions to manipulate a singly linked list.

Continued to [[Data Structures & Algorithm Lecture 14]]

# References
Continued to [[Data Structures & Algorithm Lecture 11]]

###### Information
- date: 2024.08.28
- time: 14:09


# References


###### Information
- date: 2025.08.21
- time: 19:12