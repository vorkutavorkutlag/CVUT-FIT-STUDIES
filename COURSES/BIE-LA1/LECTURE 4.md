[[LECTURE 5 (TUTORIAL)]]
Followup from the last lectures, a common question in the exams:
Given a field, determine its span.
Then, given a vector, determine if it's on the span and write it in linear dependence on the field.

$$\begin{bmatrix}1 & 2 & 3&|4\\a & b & c & | d\end{bmatrix} $$

# Solving Systems of Linear Equations
===========================================

Every SLE has either no solution, a unique solution, or more than on solution.
In depends on the domain, as in R more than one solution can imply infinite solutions, but in fields such as $Z_p$ it has finite solutions.
When a system of linear equations has at least one solution, it is called consistent.
When a system of linear equations does not have any solution, it is called inconsistent.

We now turn our attention to the problem of finding the solutions of a system of linear equations in this section. There is a systematic way to solve a system of equations, this method is called ***Gaussian Elimination*** or ***Row Reduction***.
In this method, we apply some row operations on the rows of the augmented matrix (right) of a system of equations to obtain a simpler form, called echelon form.
The latter matrix is associated to a system of equations has the same set of solutions as the first one, however, it is easier to solve.

- What are the row operations which do not change the set of the solutions?
- What is the 'Nice Form' which allows to compute SLEs easily? (Echelon Form)
- How to arrange row operations to obtain the 'Nice Form'.

For example,
$x_1 + 3x_2 -2x_3 = 5$
$2x_2 - 6x_3 = 4$
$3x_3 = 6$
This equation is easy to solve and can be computed by ***Back Substitution***. 

The augmented matrix can be rewritten as:
$$[A|b] = \begin{bmatrix}1 & 3 & -2 &|5\\0 & 2 & -6 &|4\\0 & 0 & 2 &|6\end{bmatrix}$$
Where the left side is the coefficient matrix and the right side is the augmented matrix.

For example, in the SLE:
$x + 3y -2z = 5$
$x + 5y -8z = 9$
$2x + 4y + 5z = 15$
Using back substitution, you may eliminate variables but adding or subtracting rows to create new truthful expressions. However, for a more useful solution we must use Gauss Elimination.
We must first convert into an augmented matrix.

##### Step 1
a. Replacing row 2 with row 2 minus row 1.For convenience we write as follows:
$$R_2 - R_1 \rightarrow R_2$$
b. Replacing row 3 with row 3 minus row 2. i.e.:
$$R_3 - R_2 \rightarrow R_3$$
Thus the new system of linear equations has the following augmented matrix:
$$[A_1|b_1] = \begin{bmatrix} 1 & 3 & -2 &|5 \\ 0 & 2 & -6 &|4 \\0 & -2 & 9 & |2 \end{bmatrix}$$
This is easier, as we can get rid of more coefficients by doing equal operations on different rows.
Observe that we have applied the following operations to the rows of augmented matrix in the above example:
1. Row exchange (or swap) exchanging two rows of the matrix, swapping rows i and j is denoted by $R_i \leftrightarrow R_j$.
2. Scaling (or multiplication): Multiplying a row by a non-zero scalar. Multiplying row j with a non-zero scalar c $\in$ F is denoted by $cR_j$.  
3. Row replacement (or addition): Replace row k by its sum with row j, all other rows remain intact. For any non-zero scalar $c \in F$, replacing row i by row row_i + crow+j is denoted by $R_i + cR_j$.

These three operations are called elementary row operations.
These are just fancier methods of the same ideas that we used in highschool to solve SLEs.


Two matrices can be called row equivalent if one can be obtained from the other one via elementary row operations. 
We will later discuss properties that row equivalent matrices are sharing.
Thus, the augmented matrices obtained in each steps in the above example are row equivalent.
Important fact: If we apply any of the above operations on an augmented matrix of a SLE, we obtain a new SLE which has the same set of solutions as the original one. In other words, row operations do not change the solutions of a SLE.

A matrix is said to be in **row echelon form (REF)** if it satisfies the following conditions:
1. All zero rows (i.e. the rows with all entries equal to 0) if any, are below the non-zero rows (we call a row non-zero if it has at least one non-zero entry).
In a non-zero row we call the leftmost non-zero entry the leading entry or pivot entry.
2. For any non-zero row, its leading entry is strictly to the right of the leading entries of the previous rows. In other words, in each non-zero row, the first non-zero entry is to the left of any leading (pivot) entries below.
If the matrix also satisfies the following additional property, 
then it is in ***reduced row echelon form (RREF)***:
3. Each leading entry equals 1 and is the only non-zero entry in its column.


![[Pasted image 20251009120151.png]]



There are numerous different sequences of row operations that can be used to put a matrix (or augmented matrix) into REF or RREF by using row reduction.
However, it is useful to have a standard method of choosing which row operations to apply when. With this in mind, we now present one method, called Gaussian elimination, which 
can be used to put any matrix into (not necessarily reduced) row echelon form.
Using the following matrix as an example...
![[Pasted image 20251009120605.png]]

![[Pasted image 20251009120630.png]]
![[Pasted image 20251009120711.png]]
![[Pasted image 20251009120805.png]]

At this stage, all of the remaining rows contain nothing but zeros, so we are
done—the matrix is now in row echelon form.
If this matrix represented a linear system then we could solve it via back
substitution at this point. 
However, it is sometimes convenient to go slightly farther and put the matrix into reduced row echelon form.
We can do so via an extension of Gaussian elimination called ***Gauss–Jordan elimination***, which consists of just one additional step.

![[Pasted image 20251009121108.png]]
![[Pasted image 20251009121219.png]]
![[Pasted image 20251009121257.png]]

After we have used row operations to put an augmented matrix into row echelon form, it is straightforward to find the solution(s) of the corresponding linear system just by writing down the linear system associated with that row echelon form.
However, the details can differ somewhat depending on whether the linear system has no solutions, one solution, or infinitely many solutions.
$$\begin{bmatrix} 0 & 1 & 1&|0\\0&0&1&|0\\0&0&0&|1\end{bmatrix}$$
Thus
$x_2+x_3=0$
$x_3=0$
$0=1$
With these contradictions, we say that this system has no solution.