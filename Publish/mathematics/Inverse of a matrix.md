
21-06-2024 06:40

Status : #Completed

Tags : [[Matrix]] [[linear algebra]] [[]] 

# Inverse of a matrix

If $A$ and $B$ are two non-singular square matrices of the same order such that $AB = BA = \mathbf{I}$,

where $\mathbf{I}$ is the[[ identity matrix]], then $B$ is called the inverse of $A$, i.e. $B=A^{-1}$. We say $A^{-1}$ is the inverse of the matrix $A$ if $AA^{-1}=A^{-1}A=\mathbf{I}$.

### To find the inverse matrix with the help of [[Adjoint]] matrix


$A^{-1} = \frac{\text{adj}(A)}{|A|}$

Note: 
- The necessary condition for a square matrix $A$ to possess an inverse is that the matrix $A$ is non-singular i.e., $|A| \neq 0$. 
- A square non-singular matrix $A$ of order $n$ is said to be invertible if there exists a non-singular square matrix $B$ of order $

### Properties of Inverse Matrices

• If $A^{-1}$ exists, then it is unique.
• $\left(A^{-1}\right)^{-1} = A$.
• $\left(A^T\right)^{-1} = \left(A^{-1}\right)^T$.
• Let $D = \text{diag}(d_{11}, d_{22}, d_{33}, d_{44}, \ldots, d_{nn})$, $d_{ii} \neq 0$. Then $D^{-1} = \text{diag}\left(\frac{1}{d_{11}}, \frac{1}{d_{22}}, \frac{1}{d_{33}}, \ldots, \frac{1}{d_{nn}}\right)$.
• The inverse of a [[non-singular]] [[symmetric matrix]] is a symmetric matrix.
• $\left(A^{-1}\right)^n = A^{-n}$.





# References
