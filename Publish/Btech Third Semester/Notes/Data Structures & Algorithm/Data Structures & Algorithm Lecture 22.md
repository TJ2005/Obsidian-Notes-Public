---
Title: Data Structures & Algorithm Lecture 22
Status: 
marker:
  - "[[Algorithm]]"
  - "[[Searching Algorithm]]"
  - "[[Binary Trees]]"
  - "[[Sorting Algorithms]]"
tags: 
Date: 2024.10.18
Time: 09:30
---
## Algorithm for Binary Search Tree (BST) - Finding Minimum and Maximum Nodes

#### Date: 2024-10-18  
#### Time: 09:30

#### Finding Minimum
To find the minimum value in a Binary Search Tree (BST), we need to traverse the left subtree repeatedly until we reach the leftmost node. This node will have the smallest value in the tree.
![[BTMinimum.excalidraw]]

##### Algorithm in C++:
```cpp
struct node* FindMin(struct node* T)
{
    if (T == NULL)
        return NULL;  // Tree is empty, no minimum.
    else if (T->left == NULL)
        return T;  // Found the minimum node (leftmost).
    else
        return FindMin(T->left);  // Recur to the left subtree.
}
```

- **Time Complexity:** O(h), where h is the height of the tree.
- **Explanation:** 
  - The function checks if the tree is empty. If so, it returns NULL.
  - If the left child of the current node is NULL, the current node is the minimum.
  - Otherwise, it continues searching in the left subtree.

#### Finding Maximum
To find the maximum value in a Binary Search Tree, we traverse the right subtree repeatedly until we reach the rightmost node. This node will contain the largest value.
![[BTMax.excalidraw]]
##### Algorithm in C++:
```cpp
struct node* FindMax(struct node* T)
{
    if (T == NULL)
        return NULL;  // Tree is empty, no maximum.
    else if (T->right == NULL)
        return T;  // Found the maximum node (rightmost).
    else
        return FindMax(T->right);  // Recur to the right subtree.
}
```

- **Time Complexity:** O(h), where h is the height of the tree.
- **Explanation:**
  - The function checks if the tree is empty. If so, it returns NULL.
  - If the right child of the current node is NULL, the current node is the maximum.
  - Otherwise, it continues searching in the right subtree.

#### Conclusion
- These two algorithms effectively find the minimum and maximum values in a Binary Search Tree.
- Both functions rely on the tree's structure, which ensures that the leftmost node is the smallest and the rightmost node is the largest.

#### Finding Any Element
To find any element in a  Tree, we traverse through the first node that is **Root** and based on the comparison logic on the root we decide which half we traverse next.

##### Algorithm in PseudoCode:
```js
if the tree is empty:
	return NULL
else if the item in the node equals the target
	return the node value
else if the item in the node is greater than the target
	return the result of searching the left subtree
else if the item in the node is smaller than the target
	return the result of searching the right subtree
```
##### Algorithm in CPP
```cpp
// struct node return type since element returned is a BT
// int X element to find in the binary tree
struct node* Find(struct node* T,int X);
{
	if(T==NULL)
		return NULL;
	else if(X<T->data)
		return find(X,T->Left);
	else if(X>T->data)
		return find(X,T->right);
	else
		return T;
}
```

- **Time Complexity**: O(h) where h is the height of the tree.\
- **Explanation:**
	- If the Tree is empty then return NULL.
	- If the Element to find is greater than current node then perform the find in the right node.
	- If the element to find is lesser than the current node then perform the find in the left node.
	- If the element is neither lesser neither greater than the node has to be equal to the node itself so return self.
### Insertion of elements^177580
In a binary tree before inserting a new element there can be only two possible cases.
- **Case 1**: Tree is empty.
- **Case 2**: Tree is not Empty.
	- Then the moment we find null while traversing through the BT we insert a new node.
		- Traversing algorithm can be understood by algorithm in [[Data Structures & Algorithm Lecture 22#^177580|Algorithm]] 
There is a special case where the tree already has the element. In that case we have few ways to manage the duplicate element.
- **Case 1:** U add the element towards the left of the element.
- **Case 2:** U add the element towards the right side of the element.
- **Case 3:** We add another element called frequency in the structure which will count the frequencies of a single element.
![[BTInsertion.excalidraw]]
##### Insertion of element in BT
```cpp
struct Node{
	int data;
	int *left;
	int *right;
	int frequency=1;
}
struct Node* insertElem(struct Node* Tree,int data)
{
	if(Tree==NULL){
		Tree=malloc(sizeof(Node));
		Tree->data=data;
		T->right=T->left=NULL
	}
	else if(X<Tree->data)
		Tree->left=insertElem(X,T->Left);
	else if(X>Tree->data)
		Tree->right=insertElem(X,T->right);
	else if(X==Tree->data)
		Tree->frequency++;
	return Tree;
}
```

- **Time Complexity:** O(H) since the height is
- **Explanation**: We used frequency method here.
	- If the element is bigger we insert in the right branch
	- if the element is shorter we insert in the left branch
	- if the element is equal we increase frequency

### Deletion of a node
Deletion is the most complex part in a binary tree since there is a case of having two children and managing them is a critical case as the tree is binary.
- **Case 1**: Deletion of a node which is a leaf node. Simplest case since it has no descendant
- **Case 2**: Node which has only left branch. The left branch shouldn't be deleted and should be re-linked back.
- **Case 3**: Node which has only right branch. The right branch shouldn't be deleted and be re-linked back.
- **Case 4**: Node which has both child branches. This is the most Complex Branch.
	 - Replace the key of that node with the minimum element at the right subtree.
	 - Delete That Minimum element
	 - has either no child or a child in the right since the left one is minimum but we have already found it
![[Drawing 2024-10-18 10.32.28.excalidraw]]

```js
IF T=NULL
	Display "Element not found in tree";
ELSE IF ITEM<T->DATA
	delete(T->left,item)
ELSE IF T->LEFT and T->RIGHT
	SET Temp= FindMax(T->Left)
	SET T->Data=TEMP->Data
	delete(T->left,temp->data)
ELSE
	set temp=T
	if T->LEFT=NULL and T->RIGHT=NULL
		set T=NULL
	else if T->LEFT!=NULL
		set T=T->NULL
	else
		set T=T->RIGHt
	free TEMP
```

## Example question
Make Binary tree for 24,7,16,19,52,44,42,81,31,-600.
![[exampleTree.excalidraw]]
# References


###### Information
- date: 2024.10.18
- time: 09:30