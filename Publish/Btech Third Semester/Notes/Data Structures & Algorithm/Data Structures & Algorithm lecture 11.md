---
Title: Data Structures & Algorithm lecture 11
Status: 
marker:
  - "[[Algorithm]]"
  - "[[Linked List]]"
  - "[[Lab Material]]"
tags:
  - BTech
Date: 2024.08.30
Time: 09:33
---
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