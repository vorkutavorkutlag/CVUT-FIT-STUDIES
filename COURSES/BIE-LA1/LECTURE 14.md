
The test is just until the beginning of the determinant, not including the determinant.
Knowing how to get the basis, and then being able to do change of basis.

The determinant of an invertible matrix...
For every invertible matrix A and its inverse,we see that $$1=det(I_n)=det(A^{-1}A)=det(A^{-1})det(A) \implies det(A^{-1})=det(A)^{-1}$$
In simpler terms, the determinant of the inverse of A is the inverse of the determinant of A.
In particular, if A is invertible then $det(A) \neq 0$.

As a reminder, we can compute the determinant by GEM.
Think about the proof. If R is in REF:                                   // Was late for this part. grain of salt
$det(R)=R_{11}R_{22}R_{33}$ ...

As a theorem, the determinant of the transpose of A is equal to that of A $$det(A^T) = det(A)$$
Since this holds, the statements that we knew about rows are true about columns too.

If we switch the columns of $A$, then we will have switched the rows of $A^T$
This is useful.

__Summary of properties of determinant__
- Determinant is linear in each row (column) when the other rows (columns) are fixed.
- If one interchanges two rows (columns) of a matrix, the determinant changes sign.
- For a triangular (in particular, for a diagonal) matrix, its determinant is the product of the diagonal entries.
- If a matrix has a zero row (or column) $det(A) = 0$

For any matrix $A \in M_2(F)$ , we have a definite formula for the determinant.
$$det(\begin{bmatrix}a & b \\ c & d\end{bmatrix}) = ad-bc$$
This is proven by reducing it to to REF through GEM, and treating row operations as matrix multiplications, and by properties of the determinants multiplicative principles, we can prove that the determinant will necessarily be equal to what is shown in the formula.

There also exists a formula for determinants of $A \in M_3(F)$, that works in the same way - reducing it to REF and using the properties of a matrix to evaluate the determinant of the elementary matrices (row operations). We are eventually left with:
$$det(A) = a_{11}det \begin{bmatrix}a_{22} & a_{23} \\ a_{32} & a_{33}\end{bmatrix} - a_{12}det \begin{bmatrix}a_{21} & a_{23} \\ a_{31} & a_{33}\end{bmatrix} + a_{13}det \begin{bmatrix}a_{21} & a_{22} \\ a_{31} & a_{32}\end{bmatrix}$$

Define $A(i,j)$ to be the matrix obtained from A by deleting the i-th row and j-th column. Then we can express (1) as follows:

$$det(A) = (-1)^{i+1}a_{i1}det(A(i,1)) + (-1)^{i+2}a_{i2}det(A(i,2))+a_{i3}det(A(i,3))$$
In general, for $1 \leq i \leq 3$
We call the above formula the cofactor expansion along the ith row.

Since the determinant of a matrix is equal to that of its transpose, we may derive
$$det(A) = (-1)^{j+1}a_{1j}det(A(1,j)) + (-1)^{j+2}a_{2j}det(A(2,j))+a_{3j}det(A(3,j))$$
We call the above formula cofactor expansion along j-th column.

It is important to know how to efficiently compute a determinant. 
In the next lectures we will be discussing eigenvalues and eigenvectors, and for those, we will be needing to compute the determinant.

As a theorem, the following is the cofactor expansion of determinant along k-th row:
Let $A \in M_n(F)$, $n \geq 2$, $A = (ij)^n_{i,j=1}, k \in {1,...,n}$ Then:
$$det(A) = \sum^n_{j=1} (-1)^{k+j} * a_{kj} ** det(A(k,j))$$
## Permutations
Previously, we used GEM to compute the determinants.
Now we introduce a wildly used formula for a determinant that provides it with an alternate algebraic interpretation.
It is based on permutations, which are functions that shuffle objects around without duplicating or erasing any of those objects.

If we have a mapping $f$ from one set to the same set ($f: X \rightarrow X$):
- $f$ is injective $\implies f$ is bijective
- $f$ is surjective $\implies f$ is bijective

Let $n \in N$. Every bijection $\pi : \{1,2,...n\} \rightarrow \{1,2,...n\}$ 
is called a **permutation** of set $\{1,2,...n\}$

There are $|S_n|=n!$ distinct permutations of that set, a very big number.
The set of all permutations is denoted by $S_n$.
They are denoted by small Greek letters.

Since a permutation is a mapping, permutations can be composed in the usual manner.
$\pi \circ \sigma (k)= \pi(\sigma(k))$ 
For example for the permutations:
$\pi = (3,1,5,2,4)$ and $\sigma = (1,5,4,3,2)$
It holds:
$\pi \circ \sigma$ = (3,4,2,5,1) and $\sigma \circ \pi = (4,1,2,5,3)$

Look at it as kind of a waterfall. For every number, you start with the right-most (inner-most) mapping and track your way down, feeding the output as an input to the more left (outer) mapping - usual composition logic.

Additionally, there exist inverse of permutation mappings. The identity permutations, which we denoted by $\iota$, are simply mappings that do not do anything.
As in, $\iota = (1, 2, 3, 4, 5, .. , n)$
Everything we feed into the identity, will map to itself.
The inverse of a permutation is the one that undoes it.
It holds that:
$$\pi \circ \pi^{-1} = \iota$$                                                                          and $$ \pi^{-1} \circ \pi = \iota$$
Now let us declare what a permutation matrix would be. 
Every permutation can be associated with a particular matrix by permuting the columns of the identity matrix in the manner described by the permutation. We make the following definition to make this idea precisely.
For a given $\sigma \in S_n$, the associated permutation matrix is defined: $$P_{\sigma} = [e_{\sigma(1)}|...|e_{\sigma(n)}]$$
As a theorem, we have the following.
- $P_\sigma P_T = P_{\sigma \circ T}$
- $(P_\sigma)^{-1} = P_{\sigma^{-1}}$

Then, for a given $\sigma \in S_n$
$$sgn(\sigma)=det(P_\sigma) =  [e_{\sigma(1)}|...|e_{\sigma(n)}]$$
The sign of the permutation, denoted by sgn, equals $(-1)^s$, where s is the number of times that two of its outputs must be swapped to turn it into the identity permutation.
![[Pasted image 20251127130955.png]]