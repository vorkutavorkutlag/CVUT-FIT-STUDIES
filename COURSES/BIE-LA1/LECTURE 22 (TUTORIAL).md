[[PRACTICE 9]]

Theoretical questions which may appear on the exam.

Let $V = \{\sum_{i=1}^4 c_iv_i ~|~ c_i \in Z_5 \}$ 
Is $V$ finite dimensional?

A vector space is called finite dimensional if it has a (finite) spanning list.
$V$ is the sum of $c_iv_i$, for the vectors $v_1,...,v_4$. That is, $V$ is all possible linear combinations of those vectors. That is, $V$ is equivalent to $span(v_1,...,v_4)$
The list $v_1,...,v_4$ is finite, therefore $V$ is finite dimensional.


Find an upper bound for $dim(V)$ 
That is, find a positive integer $n$ such that the dimension of $V \leq n$ 

The dimension of a vector space is the length of any basis.
Any basis is an LI list.
The length of any LI list is less than or equal to the length of any spanning list.
The length of any basis is less than or equal to the length of any spanning list.
$dim(V)=$ length of any basis $\leq |\chi|=4$    

Is there any LI list in $V$ of length 5?

The length of any LI list is less than or equal to the length of any spanning list.
Since a list of length $4$ spans $V$, and $5 \not \leq 4$, such a list does not exist.

Assume that the span of $(v_1,v_2,v_3,v_4)$ is not equal to the span of $(v_2,v_3,v_4)$, span of $(v_1,v_3,v_4)$, span of $(v_1,v_2,v_4)$, span of $(v_1,v_2,v_3)$
Is $(v_1,v_2,v_3,v_4)$ an LI list?

First, remember all possible theorems we had about LI lists.
Then, which one is useful?
In an LI list, you cannot get any vector as a linear combination of the other vectors.
Additionally, it is possible to reduce any LD list to an LI list without changing its span.
By contradiction, if $\chi$ is LD, there is a vector in $\chi$ that may be removed without changing the span. However, we see that the span changes, so we have a contradiction

What is the dimension of the span of that list?

We see that it is a spanning list (it trivially spans itself), and we have also proved that it is linearly independent. By definition, that list forms a basis. The dimension of the vector space is the length of any basis. $dim=|\chi|=4$ 

Now, rank, kernel, range

is there a matrix $A \in M_{3,5}(Z_7)$ with $rank(A)=4$ ?

Recall, the rank is the dimension of the range of the matrix.
Where the range is $\{Ax ~|~ x \in Z_7^5\} \in Z_7^3$, the span of its columns.
Recall $A \in M_{m,n}(F) \implies ran(A) \subseteq F^m$ 

Recall also that the dimension of every subspace is less than or equal to the dimension of the vector space.

Therefore, the dimension of the range of $A$ has to be less than the dimension of $Z_7^3 = 3$.
Therefore, $rank(A)$ cannot exist.

is there a matrix $A \in M_{3,5}(Z_7)$ with $rank(A)=2, dim(ker(A))=2$?
According to rank theorem, the number of columns is equal to the sum of the rank and nullity. $2+2\neq4$ Therefore, no.

Reminder that the $rank(A)$ is the number of pivots corresponding to pivot columns in the REF form of the matrix.

For the nullity, you should solve the SLE and find the basis in order to find the dimension.

Given Suppose some square matrices that by applying a sequence of row operations we obtain the identity matrix. Compute the determinant of that matrix.
Look at row operations as matrix multiplications from the left.
Then use the definition of the determinant to compute the determinant of the elementary matrices (row operations).
As a reminder, swapping = -1, scalar multiplication of row = scalar, addition (with or without scalar) = 1



To talk about the structure of the exam...

1. Spectral Theory
2. Diagonizability (Similar  matrices)
3. Change of Basis Matrices $(Z_5)$
4. Extension of LI to basis
5. Bases for $ran(A)$
6. Inverse/determinant via elementary matrices
7. Subspaces 
8. Theory
9. Some definition

==============================

To show if a matrix is diagonizable or not, we have to see if its algebraic multiplicity is equal to the geometric multiplicity

If the algebraic multiplicity is $1$, then the geometric multiplicity is necessarily also $1$
This is according to the theorem $\forall \lambda \in \sigma(A) ~ 1 \leq\mu_g(\lambda)\leq\mu_a(\lambda)$ 
