
21-06-2024 07:42

Status : #Completed 

Tags : [[mathematics]] [[Row echelon form]] [[Rank of matrix]] [[linear algebra]] 

# Minor method to find rank

The [[Matrix]] has to be non zero

Rank will be R if the matrix has
- The [[Minors]] of order R is non zero
- Every minor with order greater than R is zero



Certainly! Let’s calculate the rank of an example matrix using the minor method. We’ll follow these steps:

1. Calculate the determinant of the matrix (let’s call it ($A$)).
2. If $(\det(A) \neq 0)$, then the rank of matrix ($A$) is equal to the order of matrix ($A$).
3. If (\det(A) = 0), then the rank of the matrix is equal to the order of the maximum possible nonzero minor of the matrix.

Now, let’s consider an example matrix:

$A = \begin{pmatrix} 2 & 1 & 1 \\ 5 & 3 & 4 \\ 7 & 4 & 5 \end{pmatrix}$

$$\mathrm{Solve}\;\;\;\frac{d^{4}y}{d x^{4}}-13\frac{d^{2}y}{d x^{2}}+36y=0\,.\;\;\;\;\;.$$
First, we’ll calculate the determinant of matrix (A):

$\det(A) = \begin{vmatrix} 2 & 1 & 1 \\ 5 & 3 & 4 \\ 7 & 4 & 5 \end{vmatrix}$



Using cofactor expansion, we get:

$\det(A) = 2 \cdot \begin{vmatrix} 3 & 4 \\ 4 & 5 \end{vmatrix} - 1 \cdot \begin{vmatrix} 5 & 4 \\ 7 & 5 \end{vmatrix} + 1 \cdot \begin{vmatrix} 5 & 3 \\ 7 & 4 \end{vmatrix}$


Calculating the determinants of the 2x2 submatrices:

$\begin{align*} \begin{vmatrix} 3 & 4 \\ 4 & 5 \end{vmatrix} &= 3 \cdot 5 - 4 \cdot 4 = 1 \\ \begin{vmatrix} 5 & 4 \\ 7 & 5 \end{vmatrix} &= 5 \cdot 5 - 4 \cdot 7 = -3 \\ \begin{vmatrix} 5 & 3 \\ 7 & 4 \end{vmatrix} &= 5 \cdot 4 - 3 \cdot 7 = -1 \end{align*}$


Now, compute the determinant of (A):

$\det(A) = 2 \cdot 1 - 1 \cdot (-3) + 1 \cdot (-1) = 6$


Since $(\det(A) \neq 0)$, the rank of matrix ($A$) is equal to its order, which is 3.

Therefore, the rank of $matrix (A)$ using the minor method is 3.

Feel free to ask if you have any more questions or need further assistance! 😊

# References
