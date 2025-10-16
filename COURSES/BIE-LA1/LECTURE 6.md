
#### Linear Combination

Using elementary connectives such as vector addition, which receives $F^n, F^n$ and outputs $F^n$, scalar multiplication which receives $F, F^n$, and outputs $F^n$, and the zero vector $0 \in F^n$,
We may define linear combination for the vectors $v_1, v_2, v_3 \in F^4$ .
A span is the set of all linear combinations of the inputs, denoted by $<...>$ .

How to decide if v is in the $span(v_1, v_m)$? $\iff$ $\exists c,...,c_n \in F$ such that $v=c_1*v_1 + c_m*v_m$ $\iff$ $\exists c_1,..,c_m \in F$  s.t. (such that) $A * \begin{bmatrix}c_1 \\ ... \\ c_m\end{bmatrix} = b$
We may solve this using a series of linear equations (SLE) using Gaussian Elimination, converting it to Echelon Form and solving it by back substitution.

is $\begin{bmatrix}4 \\ 4 \\ 12 \end{bmatrix}$ in $span(\begin{bmatrix}1 \\ 2 \\ 3\end{bmatrix}, \begin{bmatrix}1 \\ 0 \\ 1\end{bmatrix}, \begin{bmatrix}0 \\ -14 \\ 2\end{bmatrix})$ ?
You may investigate if there exist $x_1, x_2, x_3 \in R$ such that:
$\begin{bmatrix}4 \\ 4 \\ 12 \end{bmatrix} = x_1 * \begin{bmatrix}1 \\ 2 \\ 3 \end{bmatrix} + x_2 * \begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix} + x_3 * \begin{bmatrix} 0 \\ -14 \\ 2 \end{bmatrix}$
By matrix representation of linear combinations we get:
$\begin{bmatrix}4 \\ 4 \\ 12 \end{bmatrix} = \begin{bmatrix}1 & 1 & 0 \\ 2 & 0 & -14 \\ 3 & 1 & 2\end{bmatrix} * \begin{bmatrix} x_1 \\ x_2 \\ x_3\end{bmatrix}$
   b    =           A          \*    x

A is the coefficient matrix.
And the augmented matrix:
$\begin{bmatrix} 1 & 1 & 0 & | & 4 \\ 2 & 0 & -14 & | & 4 \\ 3 & 1 & 2 & | & 12 \end{bmatrix}$

Solving this SLE, we receive the solutions:
$x_3 = 1/4, x_2 = 1/4, x_1 = 15/4$. Thus the above vector is in the linear span of given vectors, and:
$\begin{bmatrix}4 \\ 4 \\ 12 \end{bmatrix} = 15/4 * \begin{bmatrix}1 \\ 2 \\ 3 \end{bmatrix} + 1/4 * \begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix} + 1/4 * \begin{bmatrix} 0 \\ -14 \\ 2 \end{bmatrix}$

If the SLE is consistent, as in, has at least one solution, then it is in the span and can be written as a linear combination.

Note, this will be a part of the first exam. Given a vector, to show if it is in the span of the other vectors or not.

We may use the solutions of the SLE to better understand the properties of the vector space.



In a more difficult example, let $\begin{bmatrix}x \\ y \\ z\end{bmatrix}$ be a vector. Is it in the span of vectors $v_1 = \begin{bmatrix}1 \\ 2 \\ 3\end{bmatrix}$ and $v_2 = \begin{bmatrix}2 \\ 1 \\ 1\end{bmatrix}$ ?
It is equivalent to asking the question:
$\exists c_1, c_2 \in R$ s.t. $\begin{bmatrix}x \\ y \\ z\end{bmatrix} = c_1 * v_1 + c_2 * v_2$
Once more, we convert it into the augmented matrix where $v_1, v_2$ are the coefficients and $x, y, z$ are the solutions. 
In these cases, where we don't have constants, rather, variables x,y,z, we may indirectly prove it. If after row reduction and gaussian elimination, if we have a row that is a zero on one side, and a constant non-zero on the other side, then we have found a contradiction and prove that it is not a linear combination. However, not encountering the contradiction, we thereby show that such a linear combination is possible (if and only if the solutions match the coefficients LHS = RHS).




### Linear Independence
$F$ is an arbitrary field.
$n, m$ are positive integers
$v_1$, .., $v_m$ and b are vectors in $F^n$
$c_1, ..., c_M$ are scalars in $F$

If b is in the span then b can be written as a linear combinations of vectors with scalars.

Under which condition, on the vectors v1 ... vm, every b in the span can be written uniquely as a linear combination of vectors v1,.., vm?
To answer this question, we introduce the notation of **Linear Independence**
Correspondingly to the previous topic, in this case, we see if the SLE has no solutions.

By the term list or sequence of vectors of length n we understand the ordered n-tuple (x1, x2, xn) of vectors.
However, it is important to distinguish between **set** and **sequence/list** of vectors.
In a set, the order is not important, and in a sequence, it is important.

A list of vectors in $F^n$ is called linearly independent if the only choice of scalars that makes the sum of the vectors the zero vector is when all the scalars are equal to zero.
Observe that if the list is linearly independent and v is the span, then there are unique scalars such that $v=c_1v_1+...+c_mv_m$.

When something can be "written uniquely", it means it has only a single canonical form to write it. As in, there cannot be more than one expressions that evaluate to the same thing.


The definition of linear independence is that the zero vector can be written uniquely.
A >= 0 has a unique solution
No free variables
Every column has a pivot

More than one solution = linear dependence