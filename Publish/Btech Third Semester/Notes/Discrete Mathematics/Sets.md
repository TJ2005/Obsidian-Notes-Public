## Sets

### Definition
A set is a collection of distinct elements. For example, the set of natural numbers less than 5 can be written as:
$$
A = \{0, 1, 2, 3, 4\}
$$

### Universal Set
A universal set $U$ is a set that contains all the objects under consideration. For example, if we are discussing the set of all integers, then:
$$
U = \mathbb{Z}
$$
where $\mathbb{Z}$ represents the set of all integers.

### Subset
A subset is a set where all its elements are also contained within another set. For example, if:
$$
A = \{1, 2, 3\}
$$
then:
$$
B = \{1, 2\}
$$
is a subset of $A$, which is written as:
$$
B \subseteq A
$$

### Unions of Sets
The union of two sets $A$ and $B$ is a set containing all elements that are in either $A$, $B$, or both. For example:
$$
A = \{1, 2, 3\}
$$
$$
B = \{3, 4, 5\}
$$
The union of $A$ and $B$ is:
$$
A \cup B = \{1, 2, 3, 4, 5\}
$$

### Intersection
The intersection of two sets $A$ and $B$ is a set containing all elements that are common to both $A$ and $B$. For example:
$$
A = \{1, 2, 3\}
$$
$$
B = \{2, 3, 4\}
$$
The intersection of $A$ and $B$ is:
$$
A \cap B = \{2, 3\}
$$


### Set Difference 
Let $A$ and $B$ Be two sets. They are non empty. Then the Symmetric difference is defined as 
$$ A - B = \{ x \mid x \in A \text{ and } x \notin B \} $$ Similarly, the set difference between $B$ and $A$  is: $$ B - A = \{ x \mid x \in B \text{ and } x \notin A \} $$

### Symmetric Difference 
Let $A$ and $B$ be two non empty sets. Then the symmetric difference between $A$ and $B$ will be.
	$$ A~\oplus~B~=~ \{ ~x~|~x~\in~A~or~x~\in~B~ \}$$
Mathematically it can be represented with.
$$ A~\oplus~B~=~(~A~-~B~)~\cup~(~B~-~A)$$
Or
$$A~\oplus~B~=~(~A~\cup~B~)~-~(~A~\cap~B~)$$

### Powersets

The **power set** of a set \( S \) is the set of all possible subsets of \( S \), including the empty set and \( S \) itself. It is denoted by \( \mathcal{P}(S) \) or \( 2^S \).

#### Definition

If \( S \) is a set, then the power set of \( S \) is defined as:

$$
\mathcal{P}(S) = \{ T \mid T \subseteq S \}
$$

This means that \( \mathcal{P}(S) \) contains every subset \( T \) such that \( T \) is a subset of \( S \).

#### Example

Let \( S = \{a, b\} \). The power set of \( S \) is:

$$
\mathcal{P}(S) = \{ \emptyset, \{a\}, \{b\}, \{a, b\} \}
$$

#### Properties

1. **Cardinality**: The number of elements in the power set is \( 2^n \), where \( n \) is the number of elements in \( S \). For instance, if \( S \) has 2 elements, the power set will have \( 2^2 = 4 \) elements.

2. **Inclusion**: The empty set \( \emptyset \) and the set \( S \) itself are always included in the power set.

3. **Subset Relationship**: Every subset of \( S \) is an element of \( \mathcal{P}(S) \).

#### LaTeX Representation

In LaTeX, the power set is represented as:

```latex
\documentclass{article}
\usepackage{amsmath}

\begin{document}

The power set of a set \( S \) is defined as:
$$
\mathcal{P}(S) = \{ T \mid T \subseteq S \}
$$

For example, if \( S = \{a, b\} \), then:
$$
\mathcal{P}(S) = \{ \emptyset, \{a\}, \{b\}, \{a, b\} \}
$$

If a set \( S \) has \( n \) elements, then the power set \( \mathcal{P}(S) \) has \( 2^n \) elements.

\end{document}
```

### Cardinality of a Set

The **cardinality** of a set refers to the number of elements in the set. For a finite set, this is simply the count of elements within the set. The cardinality of a set \( A \) is denoted by \( |A| \).

#### Example

For a set \( A \) defined as:
$$
A = \{1, 2, 3\}
$$

The cardinality of \( A \) is:
$$
|A| = 3
$$

This indicates that the set \( A \) contains 3 elements.
### Partition

Let $S$ be a non-empty set. A **partition** of $S$ refers to the division of $S$ into disjoint subsets such that the union of these subsets reconstructs the original set $S$. 

In other words, a partition of $S$ is a collection of non-empty subsets $\{S_1, S_2, \ldots, S_n\}$ such that:
1. $S_i \cap S_j = \emptyset$ for all $i \neq j$ (the subsets are pairwise disjoint).
2. $\bigcup_{i=1}^n S_i = S$ (the union of all subsets equals the original set $S$).

#### Example

Consider the set $S = \{1, 2, 3, 4\}$. One possible partition of $S$ is:
$$
\{ \{1, 2\}, \{3, 4\} \}
$$

Here, the subsets $\{1, 2\}$ and $\{3, 4\}$ are disjoint and their union is $S$:
$$
\{1, 2\} \cup \{3, 4\} = \{1, 2, 3, 4\} = S
$$

### Properties of Sets

1. **Idempotent Laws**
   - For any set $A$:
     $$
     A \cup A = A
     $$
     $$
     A \cap A = A
     $$

2. **Domination Laws**
   - For any set $A$ and the universal set $U$:
     $$
     A \cup U = U
     $$
     $$
     A \cap U = A
     $$
     $$
     A \cup \emptyset = A
     $$
     $$
     A \cap \emptyset = \emptyset
     $$

3. **Complement Laws**
   - For any set $A$ and its complement $A^c$:
     $$
     A \cup A^c = U
     $$
     $$
     A \cap A^c = \emptyset
     $$

4. **De Morgan's Laws**
   - For any sets $A$ and $B$:
     $$
     (A \cup B)^c = A^c \cap B^c
     $$
     $$
     (A \cap B)^c = A^c \cup B^c
     $$

5. **Distributive Laws**
   - For any sets $A$, $B$, and $C$:
     $$
     A \cup (B \cap C) = (A \cup B) \cap (A \cup C)
     $$
     $$
     A \cap (B \cup C) = (A \cap B) \cup (A \cap C)
     $$

6. **Associative Laws**
   - For any sets $A$, $B$, and $C$:
     $$
     (A \cup B) \cup C = A \cup (B \cup C)
     $$
     $$
     (A \cap B) \cap C = A \cap (B \cap C)
     $$

7. **Commutative Laws**
   - For any sets $A$ and $B$:
     $$
     A \cup B = B \cup A
     $$
     $$
     A \cap B = B \cap A
     $$

### Cartesian Product

The **Cartesian product** of two sets is a fundamental concept in set theory and mathematics. It refers to the set of all possible ordered pairs that can be formed by taking one element from each of the sets.

#### Definition

If $A$ and $B$ are two sets, then the Cartesian product of $A$ and $B$, denoted by $A \times B$, is defined as:

$$
A \times B = \{ (a, b) \mid a \in A \text{ and } b \in B \}
$$

Here, $(a, b)$ represents an ordered pair where $a$ is an element from set $A$ and $b$ is an element from set $B$.

#### Example

Consider the sets $A = \{1, 2\}$ and $B = \{x, y\}$. The Cartesian product $A \times B$ is:

$$
A \times B = \{ (1, x), (1, y), (2, x), (2, y) \}
$$

In this example, we form ordered pairs by pairing each element of $A$ with each element of $B$.

#### Properties

1. **Order Matters**: The Cartesian product $A \times B$ is not the same as $B \times A$. For example, $A \times B$ contains pairs where the first element is from $A$ and the second is from $B$, while $B \times A$ contains pairs where the first element is from $B$ and the second is from $A$.
   
2. **Empty Set**: If either $A$ or $B$ is an empty set, then their Cartesian product will also be empty. For instance, if $A = \emptyset$, then $A \times B = \emptyset$ for any set $B$.

3. **Associativity**: The Cartesian product is associative, meaning that for three sets $A$, $B$, and $C$, the following holds:

$$
(A \times B) \times C = A \times (B \times C)
$$

However, the interpretation of the pairs differs.

4. **Number of Elements**: If $A$ has $m$ elements and $B$ has $n$ elements, then $A \times B$ will have $m \times n$ elements.

#### LaTeX Representation

In LaTeX, the Cartesian product is represented as:
```latex
\documentclass{article}
\usepackage{amsmath}

\begin{document}

The Cartesian product of two sets \( A \) and \( B \) is defined as:
$$
A \times B = \{ (a, b) \mid a \in A \text{ and } b \in B \}
$$

For example, if \( A = \{1, 2\} \) and \( B = \{x, y\} \), then:
$$
A \times B = \{ (1, x), (1, y), (2, x), (2, y) \}
$$

\end{document}

## References
```

