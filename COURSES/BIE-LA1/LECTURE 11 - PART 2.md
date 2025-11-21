[[COURSES/BIE-LA1/LECTURE 12 (Tutorial)]]

She will not accept any other way to calculate the inverse of a matrix other than what we learned in class. It is important, other than the computation, why it is true and why it works.

# Fundamental Matrix Subspaces

For any matrix $A \in M_{m,n}(F)$ we associate two subsets.
The kernel or null spaces of A, denoted by ker(A) defined by:
$ker(A) = \{v \in F^n | Av=0\} \subseteq F^n$ 
The kernel of A is also denoted by $null(A)$.
The kernel of a matrix is the set of solutions to the SLE $Av=0$.
The range of A, denoted by $ran(A)$, is defined by
$ran(A) = \{Av | v \in F^n\} \subseteq F^m$ 
The range of A is the span of its columns. Also called the column space of A.

Given a matrix $A \in M_{m,n}(F)$ we can define a transpose of $A$ by $A^T \in M_{m,n}(F)$ such that
$(A^T)_{ij}$ = $A_{ji}$ 
We turn the rows into columns and columns into rows. Similar to rotation a matrix 90 degrees clockwise.
The transpose of that matrix is also a matrix so we can define its range and kernel the same.
Therefore, we have four fundamental subspaces of a matrix:
- $ran(A)$
- $ker(A)$
- $ran(A^T)$
- $ker(A^T)$

Basis of the range. We already discussed how to obtain a basis for the span of the list of vectors. Thus by Theorem, finding a basis of the range of a matrix, we need to find a basis for the span of its columns.
After the first test, we may use: The vectors corresponding to pivot columns form a Basis.

Basis of the kernel. We need to find a basis for the set of solutions of the SLE $AX=\vec0$ 

One method to finding bases of the range and kernel of $A^T$ is to compute a REF of $A^T$ and employ the method for finding bases for the range and the kernel discussed in the previous examples. However, we will present a more sufficient way in the following.
By Theorem, $ran(A^T)$ is the span of columns of $A^T$. As columns of $A^T$ are the rows of A, we conclude that $ran(A^T)$ is the span of rows of $A$.
If $R$ is a REF of $A$ then rows of $R$ are linear combinations of rows $A$ and vise versa. Then,
$ran(A^T) = ran(R^T)$
The non-zero rows of R are linearly independent. Therefore, the non-zero rows in REF of A form a basis of $ran(A^T)$.
The kernel of $A^T$ is obtained as following. The block matrix $[A|I_m]$ can be row-reduced to $[R|E]$  where $R$ is a row echelon form of $A$. If $R$ has $k$ non-zero then the bottom $k$ rows of $E$ form a basis for $ker(A^T)$.
Therefore 
$dim(ker(A^T)) =$  the number of zero rows in REF of $A$.
$dim(ker(A)) =$ the number of free variables.


Given a matrix $A \in M_{m,n}(F)$, its **rank**, denoted by $rank(A)$, is the dimension of the range of A.
$$rank(A) = dim(range(A))$$
it follows:
- $rank(A) = dim(range(A)) =$ the number of pivot columns in REF of A
- $rank(A^T) = dim(range(A^T)) =$ the number of non-zero rows in REF of A = the number of pivots columns in REF of A.
Therefore, $rank(A) = rank(A^T)$

Then, by the **Rank Theorem**, for every$A \in M_{m,n}(F)$ we have:
- $rank(A) + dim(ker(A)) = n$
- $rank(A^T) + dim(ker(A^T)) = m$

If the kernel of A is zero then it is invertible. Now we can connect the invertibility of A to the characterization of the four subspaces.


In this lecture we decided how to decide if A is invertible, obtain inverse, obtain four fundamental inverses, and connect invertibility to the kernel. 