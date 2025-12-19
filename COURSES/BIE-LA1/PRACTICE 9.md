

Two similar matrices have several identical properties.
Given $A=PDP^{-1}$, $det(A)=det(D)$, and then likewise $P_A(\lambda) = det(D) = \prod \lambda_i$ 
Likewise, $A^{n}=PD^nP^{-1}$ 

A note. In real life, basically every matrix is diagonalizable. 
If we want to diagonalize a matrix, we have a few steps.
Given matrix $A$, we have to find its eigenvalues. Solve the characteristic polynomial for its roots, $det(A-\lambda I) = 0$
For each eigenvalue, we compare its algebraic multiplicity (root's degree in the polynomial), with the geometric multiplicity. For that, we have to find the eigenvectors related to each eigenvalue. All non-zero scalar multiples of any vector in the eigenspace are in the eigenspace (closed under scalar multiplication and vector addition).
After finding the eigenvectors, we find their basis, and the length of that basis will be the dimension of the eigenspace. The geometric multiplicity is the dimension of the eigenspace.
$P$ will consist of the vectors of the bases in a correct order!

Do not forget to write the theory and proper notation.
The characteristic polynomial is denoted as $det(A-\lambda I_n)=0 \implies det(...)=0 \implies det(...) = 0$ 

Note also that it is possible to use the cofactor expansion formula even when it is not all-zeros except the non-zero element.
The determinant of a three by there matrix: $\sum_{i=3}^3 (-1)^{i+j} * a_{ij} *\det C_{i,j}$  
Where $C_{i,j}$ is the matrix where we have deleted the cross-section of $i,j$

For a polynomial of degree $n$, you have at most $n$ real solutions, and exactly $n$ complex solutions.
The roots of the characteristic polynomial are the eigenvalues. Their algebraic multiplicities will be the degrees of the roots.

Then we want to find the eigenspace for the kernel $A-\lambda_i I_n$ for every eigenvector in our spectrum.

If we get a unique solution in the kernel, it means we have made a mistake. That is because it implies we do not have an eigenvalue. Unique solution means non-zero determinant. Non-zero determinant contradicts our characteristic polynomial definition.

Two similar matrices do not necessarily have the same eigenvectors.
This will hold only if the matrices are equivalent.
We can see this by diagonalizing them (their diagonal is the same). We see that the eigenvectors are the same if the matrix and invertible matrix pairs are the same.
And that implies the two matrices are teh same.
