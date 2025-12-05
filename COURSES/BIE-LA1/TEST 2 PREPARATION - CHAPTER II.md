
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

Another corollary states that the following statements are logically equivalent:
- $A$ is invertible
- For every $B \in F^n$, SLE $Ax=B$ has a unique solution.
- Every REF form of $A$ has a pivot in every column.
- Every REF form of $A$ has a pivot in every row.

# <u>Elementary Matrices & Matrix Inverses</u> 

An important detail we have to address first is that all row operations can be represented via matrix multiplications.
By definition, a square matrix $n \times n$ is called an elementary matrix if it can be obtained from the identity matrix via a single elementary row operation.

### Elementary Matrix Theorem (#1)
If $A, R \in M_{m,n}(F)$ and $E \in M,m(F)$ are matrices such that the block matrix $[A|I]$ can be row-reduced to $[R|E]$ then $E=RA$
Row reduction is multiplication on the left.

### Elementary Matrix Theorem (#2)
Elementary matrices are invertible.

Now, to talk about inverse matrices.
A matrix $A$ is said to be in Reduced Row Echelon Form (RREF) if:
- It is in REF
- Each pivot (leading entry) is equal to one and is the only nonzero entry in the column

A Lemma states, if $A$ is an invertible matrix in RREF, then it is equal to the identity matrix.

### Inverse Matrix Theorem (#1)
Any invertible matrix can be reduced by row operations to the identity matrix

### Inverse Matrix Theorem (#2)
If the RREF of a square matrix is the identity matrix, then the matrix is invertible.

A matrix is invertible if and only if its RREF forms the identity matrix.

If $A$ is invertible, then after row operations $E_n...E_1A = I_n$
Then, take the inverse of LHS and RHS $(E_n...E_1A)^{-1} = (I_n)^{-1} = I_n$
Then, multiply by the row operations (reapply them). We get
$A^{-1}=E_n...E_1I_n$ 
Essentially, if we do the same operations on $I_n$ as we did on $A$ to make it equal to $I_n$, we will achieve the inverse of $A$, denoted $A^{-1}$.

# <u>Fundamental Matrix Subspaces</u> 

For any matrix $A$ $\in M_{m,n}(F$) we associate two subsets:
The kernel or null space of $A$, denoted by $ker(A)$ or $null(A)$, defined by: $$ker(A)=\{v \in F^n | Av=\vec0\} \subseteq F^n$$ All the vectors in $F^n$ that, when multiplied by the matrix, result in the zero vector.

The range or image space of $A$, denoted by $ran(A)$ or $im(A)$, defined by:$$ran(A)=\{Av | v\in F^n\} \subseteq F^m$$ All the vectors in $F^m$ that we can achieve by multiplying some vector by $A$.

A proposition states that both of these subsets are subspaces, respectively of $F^n$ and $F^m$.

### Matrix Subspace Theorem (#1)
Suppose that $A \in M_{m,n}(F)$ with columns $A_1,...,A_n$. Then $$ran(A)=span(A_1,...,A_n)$$ Essentially, the range of a matrix is the span of its columns.
This justifies why we call the range of a matrix its column space.

The four subspaces $ran(A), ker(A), ran(A^T), ker(A^T)$ are called the **fundamental subspaces**.

We may achieve the basis for the range by achieving the span of the vector list consisting of the matrix' columns, and then reducing it to LI using column pivots.
If we want to find the range, we need to take column vectors which correspond to pivot columns of our REF.
We many achieve the basis of the kernel, we need to find the basis for the set of solutions of the SLE $Ax=\vec0$. We do it by finding what constraints are applied on any vectors in that set, and that, in return, will return a span, that we can then reduce to LI using column pivots.

One method of finding bases for the range and kernel of $A^T$ is to compute REF of $A^T$ and employ the method for finding bases for range and kernel discussed previously. However, there exists a more efficient method.
By theorem, $ran(A^T)$ is the span of columns of $A^T$. As columns of $A^T$ are the rows of $A$, we conclude $ran(A^T)$ is the span of the rows of $A$. 

We take the REF and take the non-zero rows from our REF.
If $R$ is REF of $A$ then rows of $R$ are linear combinations of rows of $A$ and vice versa. Thus, $$ran(A^T) = ran(R^T)$$ The non-zero rows of R are linearly independent. **Thus non-zero rows in REF form a basis for $ran(A^T)$.**

Let $A \in M_{m,n}(F)$. We use the following result to obtain $ker(A^T)$
The block matrix $[A|I_m]$ can be row-reduced to $[R|E]$ where $R$ is REF of $A$.
If $R$ has $k$ zero rows, the bottom $k$ rows of $E$ form a basis of $ker(A^T)$

To summarize how to find all the bases of fundamental subspaces...
Let $A \in M_{m,n}(F)$. 
We can find bases of the four subspaces by row reducing $[A|I_n]$ to REF $[R|E]$ 
- The non-zero rows of $R$ form a basis for $ran(A^T)$
- The rows of $E$ beside the zero rows of $R$ form a basis of $ker(A^T)$
- The columns of A corresponding to leading columns in $R$ form a basis of $ran(A)$.
- A basis for $ker(A)$ can be achieved by solving for pivot variables in terms of free variables in SLE $Rx=\vec0$ 

# <u>Change of Bases</u> 

A finite dimensional vector space has more than one basis. Let $\beta, \alpha$ be two bases for a vector space $V$. Then for any $v \in V$, one can compute two column vectors $[v]_A$ and $[v]_B$, the coordinate of the vector with respect to the bases.

Let $A=(v_1,...,v_n)$ and $B$ be two bases of a vector space $V$ over field $F$. The **change of basis matrix** from $A \rightarrow B$ is denoted by $[I]_{B \leftarrow A} \in M_n(F)$ who's columns are $[v_1]_B...[v_n]_B$

### Change of Basis Theorem (#1)
Suppose that $A, B$ are two bases for vector space $V$ over field $F$. Then:
- $[v]_B = [I]_{B \leftarrow A} [v]_A \forall v \in V$
- $[I]_{B \leftarrow A}$ is an invertible matrix, with inverse $[I]_{A \leftarrow B}$
moreover, $[I]_{B \leftarrow A}$ is a unique matrix satisfying the first item.
As in, there is only one change of basis matrix.

The change of basis from $B$ to the standard basis is the matrix whose columns consist of vectors from $B$.
That is because any vector with respect to the standard basis is itself.


### Change of Basis Theorem (#2)
Let $V$ be a finite dimensional vector space, suppose that $A, B, Y$ be bases for $V$. Then: $$[I]_{B \leftarrow A} = [I]_{B \leftarrow Y}[I]_{Y \leftarrow A}$$
Author's note: when computing the change of basis matrix from the standard basis to some basis B, that is applying the mapping that is that matrix onto some vector, it is easier to first compute the change of basis matrix from B to the standard basis, which would simply form a matrix whose columns consist of the B basis' vectors. After that, we take its inverse, and with the first theorem, we find the change of basis matrix from standard basis to basis B. 
In short, the change of basis matrix from standard basis to basis B, is the inverse of matrix $B'$, which is a square matrix who's columns consist of vectors of $B$.
Then, to find the vector with respect to the basis, we apply the change of basis vector by multiplying from the left.

When computing a change of basis matrix in a test, it is sufficient to simply find the matrices corresponding to the matrix multiplication. You will need to inverse one matrix to use the first theorem, however, there is no need to multiply matrices together. Your final answer can be (SOME MATRIX) (SOME OTHER MATRIX) (VECTOR). However, it has to be with the actual numbers inside of them.  You need to compute the matrices, but not their multiplication.

# <u>Author's Wildcards</u> 
Linear dependency lemma: when reducing a list to LI, the vectors corresponding to the columns with no column pivots are redundant, and are actually linear combinations of other vectors. Then, removing them, we use another lemma that a list whose all columns have pivots is LI.

By the rank theorem, we know that if a matrix isn't invertible then its kernel is not just the zero vector.

Pivots...
All row pivots $\implies$ spanning
All column pivots $\implies$ LI
For a matrix to be invertible, its columns should form a basis, meaning it should contain a pivot in every column (LI) and a pivot in every row (spanning)
When we want to find the dimension of the range of a matrix, we look at its corresponding column pivots.
When we want to remove a redundant vector, we look at columns with no column pivots. Taking them out will not change the span