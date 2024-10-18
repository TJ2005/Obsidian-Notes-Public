---
Title: Data Structures & Algorithm Lecture 19
Status: 
marker: 
tags: 
Date: 2024.10.04
Time: 09:21
---
# Representation of Binary Tree Using Indexing in arrays

In a binary tree, each node has up to two children: a left child and a right child. If we store the nodes of the binary tree in an array or a list, we can represent the tree using an index-based approach. In this scheme, for a node at index `p`:

- The **left child** of the node is at index `2p + 1`
- The **right child** of the node is at index `2p + 2`

#### Example

Consider the following binary tree:
```
        A (0)
       /   \
    B (1)   C (2)
    /  \    /  \
  D (3) E (4) F (5) G (6)
```

If the root `A` is at index `0` (p = 0), the left child `B` is at `2*0 + 1 = 1`, and the right child `C` is at `2*0 + 2 = 2`. This pattern continues for every node:

- For `B` at index 1:  
  - Left child (`D`): `2*1 + 1 = 3`
  - Right child (`E`): `2*1 + 2 = 4`

- For `C` at index 2:  
  - Left child (`F`): `2*2 + 1 = 5`
  - Right child (`G`): `2*2 + 2 = 6`

#### Formula Breakdown:
- **Left Child**:  
  For a node at index `p`, the left child is found at `2p + 1`.
  
- **Right Child**:  
  The right child is found at `2p + 2`.

This representation is particularly useful when implementing binary trees in arrays because it allows us to calculate child and parent positions efficiently. The parent of a node at index `i` can be found using the formula `floor((i-1)/2)`.

#### Note on Root:
The root of the binary tree is always at index `0`.

### Advantages of Array Representation
1. **Space-Efficient**: No need for pointers or links between nodes, just index calculation.
2. **Easy Traversal**: Child and parent nodes can be accessed using simple arithmetic operations.

This approach is commonly used in heaps, where the structure of a binary tree is implemented using an array

### Array Representation of a Binary Tree

In an array representation of a binary tree, each node is stored in an array or list based on its level-order traversal. The relationship between parent and child nodes is maintained through indexing.

#### Example Binary Tree:

```
        A
       / \
     B     C
    / \   / \
   D   E F   G
```

The array representation of the above binary tree is as follows:

| Index | Node |
|-------|------|
| 0     | A    |
| 1     | B    |
| 2     | C    |
| 3     | D    |
| 4     | E    |
| 5     | F    |
| 6     | G    |

#### Array Representation:

```
[A, B, C, D, E, F, G]
```

#### Parent-Child Index Relationship:

For a node at index `p`:
- **Left Child**: `2p + 1`
- **Right Child**: `2p + 2`
- **Parent**: `floor((p - 1) / 2)`

#### Example Breakdown:

- Node `A` is at index `0`.  
  - Left child of `A` (`B`): `2*0 + 1 = 1`  
  - Right child of `A` (`C`): `2*0 + 2 = 2`

- Node `B` is at index `1`.  
  - Left child of `B` (`D`): `2*1 + 1 = 3`  
  - Right child of `B` (`E`): `2*1 + 2 = 4`

- Node `C` is at index `2`.  
  - Left child of `C` (`F`): `2*2 + 1 = 5`  
  - Right child of `C` (`G`): `2*2 + 2 = 6`

#### Advantages of Array Representation:
- **Efficient access** to parent and child nodes.
- **Compact storage** with no need for pointers or references, just an array.



# Representation of Binary Trees in Linked List
In a binary Tree made with linked list the structure is made with a node that has two addresses. These two addresses are of their child nodes and not the parent nodes. DO NOT MISTAKE THIS FOR DOUBLE LINKED LIST.

### Address
The addresses points towards the both the child. Thus the node needs two addresses.
![[Representation of Binary tree in linked list.excalidraw]]
# Traversal of Binary Tree
The traversal needs a specific node then it goes to the left node first then the right node

```cpp
Algorithm binaryPreorder(T,v):
	perform the "visit" action for node v
	if v has a left child u in T then
		binaryPreorder(T,u) //recursively traverse left subtree
	if v has a right child in T then
		binaryPreorder(T,W) //recursively traverse right subtree

```

Let's enhance the note with more details on binary trees, linked lists, and tree traversal algorithms.

# Representation of Binary Trees in Linked List

In a binary Tree represented with a linked list, each node contains two addresses pointing to its child nodes, not the parent nodes. This structure should not be confused with a doubly linked list.

### Node Structure
Each node in the binary tree has two pointers:
- `left`: points to the left child node
- `right`: points to the right child node

```cpp
struct TreeNode {
    int data;
    TreeNode* left;
    TreeNode* right;
};
```

### Address
Each node in the binary tree has two addresses pointing to its left and right child nodes, respectively.

### Advantages of Linked List Representation
- **Dynamic Size**: Nodes can be added or removed without worrying about reallocation or resizing.
- **Efficient Memory Usage**: Only the required nodes are allocated memory.
# Traversal of Binary Tree
Traversal of a binary tree involves visiting a specific node, then recursively visiting the left child node, followed by the right child node.

#### Pre-order Traversal
In pre-order traversal, the nodes are recursively visited in this order: root, left, right.

```cpp
Algorithm binaryPreorder(T, v):
    perform the "visit" action for node v
    if v has a left child u in T then
        binaryPreorder(T, u) // recursively traverse left subtree
    if v has a right child w in T then
        binaryPreorder(T, w) // recursively traverse right subtree
```

#### In-order Traversal
In in-order traversal, the nodes are recursively visited in this order: left, root, right.

```cpp
Algorithm binaryInorder(T, v):
    if v has a left child u in T then
        binaryInorder(T, u) // recursively traverse left subtree
    perform the "visit" action for node v
    if v has a right child w in T then
        binaryInorder(T, w) // recursively traverse right subtree
```

#### Post-order Traversal
In post-order traversal, the nodes are recursively visited in this order: left, right, root.

```cpp
Algorithm binaryPostorder(T, v):
    if v has a left child u in T then
        binaryPostorder(T, u) // recursively traverse left subtree
    if v has a right child w in T then
        binaryPostorder(T, w) // recursively traverse right subtree
    perform the "visit" action for node v
```

## Example

###### Information
- date: 2024.10.04
- time: 09:21>)