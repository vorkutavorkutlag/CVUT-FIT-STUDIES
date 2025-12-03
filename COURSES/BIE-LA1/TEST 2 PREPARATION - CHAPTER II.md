
If you have reached it this far...
- You have either read the entirety of the previous chapter and felt confident enough to continue to the new topics. In which case, congratulations! It gets way worse now.
- You have skipped the first chapter because you are arrogant and think you are better than it. In which case, we'll see how you feel after this one.


# CHAPTER II - Invertible Matrices, Elementary Matrices, Matrix Inverses, Fundamental Matrix Subspaces, Change of Bases, Fields

# <u>Invertible Matrices</u> 
Let us first define invertible matrices.
Let $F$ be a field.
Matrix $A \in M_n(F)$ is called invertible (regular) if there exists matrix $B \in M_n(F)$ such that $$AB=BA=I_n$$
Matrix $A$, which is not invertible, is called singular.
To clear some things up:
- Matrix with a single subscript ($M_n$) denotes a square $n \times n$ matrix.
- $I_n$ denotes the identity matrix. It is a $n \times n$ square matrix with $1$'s in the diagonal and $0$'s everywhere else. Applicable for any $n \in N$
Above is the matrix multiplication of the two matrices. Matrix multiplication from the left is the application of a mapping.
Matrices in general can be viewed as functions, taking in vectors (or other matrices) that have the same number of rows as this matrix has columns.
As a reminder, $M_{rows, columns}$

Every matrix, if it is invertible, has a unique inverse. We denote it by $A^{-1}$ and called it the inverse matrix of A. 

Note that an invertible matrix has to be a square matrix.
Moreover, if there exists a matrix $B$ such that $AB=I_n \lor BA=I_n$ we skip the proof.

### Invertible Matrix Theorem (#1)
If $A$ and $B$ are invertible matrices, then $AB$ is invertible and $$(AB)^{-1}=B^{-1}A^{-1}$$
Onto transposes.
Let $A \in M_{m,n}(F)$. We define $A^T$, called transpose of $A$, by transforming every row into a column, and every column into a row. For example $$(\begin{bmatrix}1 & 3 & -1 \\ 0 & 9 & -5\end{bmatrix})^T = \begin{bmatrix}1 & 0 \\ 3 & 9 \\ -1 & -5\end{bmatrix}$$
A Lemma for transposes:
Let $A \in M_{m,n}(F)$ and $B \in M_{n,k}(F)$ then $(AB)^T=B^TA^T$ 

### Invertible Matrix Theorem (#2)
Let $A \in M_n(F)$ be an invertible matrix. Then $A^T$ is as well invertible. It holds $$(A^T)^{-1}=(A^{-1})^T$$
### Invertible Matrix Theorem (#3)
Let $A \in M_n(F)$. Then $A$ is invertible $\iff$ for any RHS $b \in F^n$, the SLE $Ax=b$ has a unique solution. In other words, if the columns of $A$ form a vector list that is LI, and span $F^n$, it is invertible. LI because it has at most one solution, and span because it has at least one solution.
Author's note: An intuitive way to think about this is considering where invertible matrices are used. If we 'lose information' during matrix multiplication, for example multiply by zero column, even if we know our resulting vector/matrix, and the matrix we used for the multiplication, we won't be able to find the exact vector/matrix we applied the operation on. There is more than one vector/matrix that would satisfy it. We cannot properly inverse it. It is not invertible.

The following corollaries can be concluded from the above theorem:
- $A$ is invertible $\iff (A_1,...,A_n)$ is a spanning list in $F^n$
- $A$ is invertible $\iff (A_1,...,A_n)$ is an LI list.
- $A$ is invertible $\iff$ $(A_1,...,A_n)$ form a basis for $F^n$

// I need to double-check this with TA
// Is only one of these enough, or only all of them at once?

Another corollary states that the following statements are logically equivalent:
- $A$ is invertible
- For every $B \in F^n$, SLE $Ax=B$ has a unique solution.
- Every REF form of $A$ has a pivot in every column.
- Every REF form of $A$ has a pivot in every row.

# <u>Elementary Matrices & Matrix Inverses</u> 
