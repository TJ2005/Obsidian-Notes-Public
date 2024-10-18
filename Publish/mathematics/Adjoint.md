
20-06-2024 23:05

Status : #Completed

Tags : [[mathematics]] [[Matrix]] [[linear algebra]]

# Adjoint


let $A = [a_{ij}]$ be a matrix 
write all cofactors of the set $A$ and then write all of them in a matrix
the transpose of the matrix $A_{ij}$ is called adjoint matrix 


Let $A = \begin{pmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \\ \vdots & \vdots & \ddots & \vdots \\ \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{pmatrix}$ be an m x n square matrix.

The minor of element $a_{ij}$ is denoted by $M_{ij}$ and is the determinant of the submatrix obtained by deleting the $i^{th}$ row and $j^{th}$ column of A. We can express this using the following code:

$$\begin{equation}
M_{ij} = \det \begin{pmatrix} ... & a_{1j} & ... \\ \\ ... & a_{{i-1},j} & ... \\ \\ ... & a_{{i+1},j} & ... \\ \\ ... & a_{mj} & ... \end{pmatrix}
\end{equation}$$

The cofactor of element $a_{ij}$ is denoted by $C_{ij}$ and is calculated as follows:

$$\begin{equation}
C_{ij} = (-1)^{i+j} \cdot M_{ij}
\end{equation}
$$
where $(-1)^{i+j}$ is 1 if the sum of i and j is even, and -1 if the sum is odd.

To find all the cofactors of matrix A, we can calculate the minor for each element and multiply it by the corresponding $(-1)^{i+j}$ term. These cofactors can then be arranged into a new matrix, called the cofactor matrix, denoted by $C_A$.



# References
