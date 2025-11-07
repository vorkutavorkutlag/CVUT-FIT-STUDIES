
[[PRACTICE 3]]
### More on bases...
If V is finite dimensional, then by the definition, it has a spamming sequence B. Then we have one of the following cases.
If $B$ is linearly independent, then it is a basis for $V$.
If $B$ is linearly dependent, then by a remark in the previous section we can remove some vectors from  to obtain a linearly independent sequence $B'$ while the span of the new sequence is the same as the span of $B$. Thus  is linearly independent and spans , thus $B'$ is a basis for $V$.

The length of the basis is equal to the dimension. The dimension of the vector space is the length of the basis. For $R^3$, the basis will include 3 elements.

Consider two bases X and B. B is spanning and LI, X is LI and spanning.
Because X is LI and B is spanning: $|X| \leq |B|$
Because X is spanning and B is LI: $|B| \leq |X|$
Therefore, $|B| = |X|$ 

What is the length of basis of $M_{2,2}(Z_{17})$?
$|E_{11}, E_{12}, E_{21}, E_{22}|$ = 4. Therefore, the dimension of $M_{2,2}(Z_{17})$ = $dim(M_{2,2}(Z_{17})) = 4$

Every LI list can be expanded to a basis,
Every spanning list can be reduced to a basis.
## Inverse Matrices
Let F be a field.
$I_n$ is the identity matrix is a square matrix where all the elements on the main diagonal are 1, and all other elements are 0. It acts like the number 1 in matrix multiplication, meaning that multiplying any matrix by the identity matrix leaves the original matrix unchanged.
By definition, Matrix $A \in M_n(F)$ is called **invertible (regular)** if there exists matrix $B \in M_n(F)$ such that $AB = BA = I_n$
Matrix A, which is not invertible, is called singular.

Observe that if A is invertible then there is a unique matrix B satisfying $AB=BA=I_n$. To see this, if C is another matrix such that $CA=AC=I_n$, we show that B = C. Indeed,
$$B=BI_n=B(AC)=(BA)C=I_nC=C$$
Since B is a unique matrix satisfying $AB=BA=I_n$, we refer to it as $A^-1$ and call it the inverse matrix of $A$.

Note that an invertible matrix should be a square matrix.
Moreover, if there exists a matrix B such that either $AB=I_n$ or $BA = I_n$, then A is invertible, and we skip the proof.

If A and B are invertible matrices then AB is invertible and $(AB)^-1 = B^-1A^-1$
Note that for matrices A and B of size n
$B^{-1}A^{-1}AB = B^{-1}I_nB = B^{-1}B = I_n$

Let $A \in M_{n,n}(F)$. Then, A is invertible if and only if for any right side $b \in F^n$ the system of linear equations $Ax = B$ has a unique solution.

A matrix is invertible only if its columns are a basis of the field (spanning list that is linearly independent).