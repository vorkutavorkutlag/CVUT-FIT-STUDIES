[[COURSES/BIE-LA1/LECTURE 14|LECTURE 14]]
Computing the determinant!
In order to find eigenvalues (next lectures) we really should know how to compute the determinant.
For example, for the matrix $A = \begin{bmatrix}5 & 6 & -3 \\ 0 & -2 & 3 \\ 2 & 4 & -1 \end{bmatrix}$ we should use the expansion formula along the first column. Then, the determinant will be $det(A)=(-1)^{1+1}3 * det \begin{bmatrix} -2 & 3 \\ 4 & -1 \end{bmatrix} + 0 + (-1)^{3+1} * 2 * det \begin{bmatrix} 6 & 3 \\ -2 & 3 \end{bmatrix}$ 
Now, with $2 \times 2$ matrices, we are able to use the formula and derive that $det(A)=-6$
Alternatively, we are able to use row operations on it to make it into REF, at which point the determinant would be the product of the diagonal elements, in a product with the row operations (multiplications).
For upper triangular matrices the determinant $det(R) = R_{11} * R_{22} * R_{33}$
This is a theorem and we don't need to rove it, however, it's nice to know that if we use the definitions of the determinants with elementary matrices with scalar multiplication (division by the pivots) we achieve that the determinant is the product of the diagonal elements.
