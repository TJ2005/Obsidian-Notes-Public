---
Title: Data Structures & Algorithm & Algorithm Lecture 19
Status: 
marker:
  - "[[Data Structures & Algorithm]]"
  - "[[Trees]]"
  - "[[File Storage]]"
  - "[[Introduction]]"
  - "[[Traversal]]"
  - "[[Binary Trees]]"
  - "[[Algorithm]]"
tags:
  - BTech
Date: 2024.09.27
Time: 09:13
---
# Unit 4: Non-Linear Data Structures (Trees)

This unit covers **Non-Linear Data Structures**, focusing primarily on **Trees**, which are often implemented using linked lists.

## 1. Introduction
- Trees are hierarchical structures, unlike linear structures such as arrays or linked lists.
- They consist of nodes connected by edges, with a single node called the **root** and subsequent **child** nodes forming subtrees.
### 1.1 Definition of tree
A tree is a finite set of one or more nodes such that
- There is a specially designated node called root.
- Remaining of them are called child nodes.
Example: Operating System, Java

### 1.2 Tree: Basic Terminologies
There are terms to remember
- Node and Link
	- is the main component of any tree structure. The concept of node is same as as used in linked list. Node of a tree store the actual data and links to the other node
	- Link is a pointer to a node in tree
- Root
- Sub Tree
- Ancestor Descendant
- Parent Children
	- Parent of a node is the immediate predecessor of a node the immediate predecessor of a node are known as a child
- Siblings
- Edge / Paths


## 2. Binary Tree
- A **binary tree** is a tree in which each node has at most two children, commonly referred to as the **left child** and **right child**.
  
## 3. Representation of Binary Trees in Memory
- Binary trees can be represented in memory using **linked lists** or **arrays**.
  - **Linked List Representation:** Each node contains a value, a reference to the left child, and a reference to the right child.
  - **Array Representation:** Nodes are stored in a sequential manner where the left child is located at index `2*i + 1` and the right child at `2*i + 2` for a node at index `i`.

## 4. Binary Tree Traversal Algorithms
Traversal refers to visiting all the nodes in the binary tree in a systematic way. There are three primary traversal methods:

### 4.1 Inorder Traversal (LVR)
- **Order:** Left, Visit, Right
- The left subtree is visited first, then the root node, followed by the right subtree.

### 4.2 Preorder Traversal (VLR)
- **Order:** Visit, Left, Right
- The root node is visited first, followed by the left subtree, then the right subtree.

### 4.3 Postorder Traversal (LRV)
- **Order:** Left, Right, Visit
- The left subtree is visited first, then the right subtree, and finally the root node.

![Figure: Node Traversal](Figure%20Node%20Traversal.excalidraw.md)

## 5. Construction of Binary Tree from Traversals
- Given any **two traversal sequences** (inorder, preorder, or postorder), you can reconstruct the binary tree.
  - Example: Using **inorder** and **preorder** traversals, you can construct the original binary tree.

## 6. Binary Search Tree (BST): Insertion & Deletion
- A **Binary Search Tree** (BST) is a special type of binary tree where:
  - The left child contains values **less than** the parent node.
  - The right child contains values **greater than** the parent node.
  
### 6.1 Insertion
- Inserting a new node involves comparing the value with the root. If it’s smaller, it goes to the left; if it’s larger, it goes to the right.

### 6.2 Deletion
- Deletion of a node involves three cases:
  - **No children:** Simply remove the node.
  - **One child:** Remove the node and connect its child to its parent.
  - **Two children:** Replace the node with its inorder successor or predecessor.

## 7. Application of Tree Data Structures: Expression Trees
- **Expression Trees** are a common application of trees, where internal nodes represent operators and leaf nodes represent operands. These are used to evaluate mathematical expressions.

![Figure: Node Structure](Figure%20Node%20Structure.excalidraw.md)

## Depth Level of a tree
Depth of the v is the no. of ancestors of v. excluding v itself or the number of parent node corresponding is given a node of the tree.
```algorithm
Algorithm dept(T,v):
	if v is ithe root of T then
		return 0
	else
		return 1+depth(t,w), where w is the parent
```


![[tree depth map.excalidraw]]
## Height of node
if v is the external node then the height of v is 0
Else, The height v is j + max height of the child of V
```algorithm
Algorithm height(node)
	if node is leaf:
		return 0
	else
		return height(node.child)
		
		
```
## General Terms
### Path Length
The number of edges on the path from a node to another
### Size of a node
The number of descendants the nodes has is a size of a node.
# Binary Tree
Binary tree is a finite sets of nodes such that
- T is empty called empty binary tree
- T contains a specially designated node called the root of T and the remaining node of I form type 

### Proper Strict Binary Tree
is a special type of binary tree in which every parent node/internal node has either two or no children. i.e. all nodes except leaf nodes have two children.
### Complete Binary Tree
It is a binary tree in which of the levels are completely filled except possibly the lowest one, which is filled from the left.
- Every Level Except the last level must be completely filled.
- All the leaf elements must lean towards the left.
- The last leaf element might not have a right sibling i.e. a complete binary tree doesn't have to be a full binary tree.
![[proper Binary Tree.md]]

## Properties of Binary Tree
level d has at most 2d nodes
Minimum number of nodes possible is $2^{h+1}-1$
Minimum Number of nodes possible in a binary tree of height $h$ $h+1$






---

### References

- **Date:** 2024-09-27
- **Time:** 09:13
