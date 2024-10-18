---
Title: Data Structures & Algorithm Lecture 21
Status: 
marker:
  - "[[btech]]"
  - "[[Algorithm]]"
tags: 
Date: 2024.10.16
Time: 14:10
---
# Construction of Binary Tree from Given Traversals

## Given Traversals
- **Inorder**: `[10, 4, 18, 22, 9]`
- **PostOrder**: `[10, 18, 9, 22, 41]`

---

## In-order + Post-Order Traversal

In the **inorder traversal**, the process follows **Left-Vertex-Right**. To understand this better, let’s look at an example:

1. The first element in the inorder sequence is considered part of the left subtree.
2. The next element is considered the root (vertex).
3. The remaining elements are assumed to be part of the right subtree.
4. The remaining subtree is further broken down in a similar manner, recursively applying the process.

### Example 1:
![](InorderTraversalReverseEx1.excalidraw.md)

---

### Example 2:
**Inorder Traversal**: `4 2 5 1 6 3`

![](InorderToBinaryTreeReverse2.excalidraw.md)

---

### Example 3:
**Inorder Traversal**: `4 2 1 7 5 8 3 6`

![](InorderToBinaryTreeReverse3.excalidraw.md)

---

## Post-order Traversal

In the **PostOrder Traversal**, the process follows **Left-Right-Vertex**. We apply the PostOrder traversal language to construct the tree.

---
## In-order + Post-order
Inorder: {DBEAFC}
Postorder:{ABDECF}

## References

---

###### Information
- **Date**: 2024.10.16
- **Time**: 14:10
********