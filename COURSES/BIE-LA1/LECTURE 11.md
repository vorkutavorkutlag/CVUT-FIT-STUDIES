[[COURSES/BIE-LA1/LECTURE 11 - PART 2]]
### ...Matrix invertibility

$A$ is invertible if and only if $Ax=b$ has a unique solution where $BA = I_n$
Find a solution, put them in a matrix, and you will get the inverse of the matrix.
It is not a very efficient way. If a matrix is 5x5, you need to solve 5 SLEs. There exists a more efficient way to invert a matrix.
Let's look at row operations and GEM in a different way.
For every matrix operation, it can be expressed as a multiplication of that matrix.
$A_1 = E_1A$ where A is the original matrix, and E is the operation.
$A_n=E_nA_{n-1}$ 
$E$ is always invertible, being an elementary matrix.

In order to use the remark of invertibility of matrices, we first bring the following definition.
A matrix $A$ is said to be **Reduced Row Echelon Form** (RREF) if it is in REF, and each pivot (leading entry) is equal to 1 and is the only non-zero entry in the column.

If and only if $A$ is an invertible matrix in the reduced row echelon form, then A is equal to the identity matrix. Since $A$ is invertible, every column has a pivot. As we assume that $A$ is in RREF, $A$ should be equal to the identity matrix.

$A$ is invertible $\iff$ $A$ has a pivot in every column

$A$ is invertible if and only if its RREF is equal to the identity matrix. Then the matrix you used to get from $A$ to the $I_n$ is the inverse of $A$ such that $A * A^{-1} = I_n$.
Starting from $[A | I_n] \rightarrow ... \rightarrow [R|E]$ 
If $R \neq I_n \implies A$ is not invertible
If $R = I_n \implies A$ is invertible, and $A^{-1}=E$

If there exists row or columns in REF of A with no pivot, $A$ is not invertible.
Otherwise, $A$ is invertible, and we need to continue to obtain RREF.