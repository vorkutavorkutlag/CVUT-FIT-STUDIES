[[COURSES/BIE-LA1/LECTURE 16|LECTURE 16]]
The idea today is not really structured, we'll be bouncing around some topics. Fun!

The matrix space forms a vector space.
$M_{m,n}(F)$ is closed under vector addition and scalar multiplication.
Matrices are also considered as vectors.
While It is a vector space in of its own, we can consider elements of the space as functions.
Every matrix multiplication is like feeding an input to the function.
The number of rows of an input vector corresponds to the number of columns of the matrix, and the matrix' number of rows corresponds to the number of rows of the output vector.
Additionally, matrix multiplication can be split by addition, and by scalar multiplication.
This is linearity of functions. Matrices are linear functions.

Why do we care?
Every vector is in a vector space, and vector spaces have bases.
For example, given a vector  $v = \begin{bmatrix} a_1 \\ a_2 \\ a_3 \end{bmatrix}$ can be represented as $a_1\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} + a_2\begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix} + a_3\begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}$
Therefore, any vector multiplication$Av$ can be viewed as $Av=A(a_1\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} + a_2\begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix} + a_3\begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix})$
Therefore, using the linearity of matrices, we can view it as $$a_1A\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} + a_2A\begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix} + a_3A\begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}$$


Every matrix is uniquely determined by its values in the standard basis.
Meaning, if you tell me what a matrix does on a basis, we can tell what it does on every other vector. This will play into change of basis.

Then, let us consider all the vectors that satisfying $Av=\vec0$
Consider again $A \in M_{m,n}(F)$. Then $Av=\vec0$ implies $v \in F^n$ and $\vec0 \in F^m$
Our domain is the number of columns, our 'image' is the number of rows.

If we want to consider the set of vectors $\{v \in F^n | Av =\vec0\}$ It would be a subset of $F^n$.
We denote this subset as the kernel of A $ker(A)$. Also known as the null space and nullity.

Okay, let's sidetrack, we will have true or false questions in the test. They will look like this.
It's usually good to do these questions first in a test.
"True/False: Does there exist an LI list of length 7 in $Z_{13}^5$ "
The proper way to answer this would be is to say something like:
$dim(Z_{13}^5)=5$ Because any basis of $Z_{13}^5$ is of length 5. According to a theorem, all bases have the same length. By a theorem, the length of every LI vector list is less or equal to the dimension. $7 \leq 5$ is a contradiction, therefore this is false.
This is not the type of question where you can provide a counterexample, since this question's quantifier is the existence.

"True/False: There is a spanning length of length 4 in $R^3$"
To show it's true we only need to provide an example, as we are dealing with an existential quantifier. We could use the theorem for the length of the spanning list, but a safer bet would be to provide an example.

For True questions, if they are universal, provide a theorem. If they are existential, provide an example.
For False questions, if they are universal, provide a counterexample. If they are existential, provide a theorem.

-- Side-note: we should also be able to find the bases of fundamental subspaces, compare the spans of two vector lists, extended LI to basis, find matrix inverses.

"True/False: For each LI list L of length 7 in $R^7$, L spans $R^7$"
It is universal and true, so we want to provide a theorem.
By theorem, every spanning list is greater or equal to the dimension, and every LI list is less or equal to the dimension, and when they coincide, then the list is both spanning and LI.
Another theorem we have is: every LI list of length $n$ in $F^n$ is a basis for the space.


Feel free to use anything in the slides, just use it correctly.


We will definitely have a problem to compute the kernel.
The kernel will always contain the zero vector, but it may contain more than one if the columns of a matrix form an LD list of vectors. For example, if we have the zero matrix in $M_{m,n}(F)$ then the kernel will be all the possible vectors, $F^n$

When computing a kernel, the broad idea is we do GEM until we get to REF. Since every matrix corresponds to an SLE. 
What I would probably say before this is that we want to analyse this SLE induced by the matrix so we compute GEM to get REF. Once we get there, we can explain what we are doing to zero. Say something like we want to compute the kernel, and we do this by analyzing the SLE and we're going to compute the REF.
We could augment it with zero, but that is not necessary since no row operations change the zero matrix.

Once we reach REF, a case that could occur is that we may use backward substitution and show that there is only one unique solution as there are no free variables. Therefore, the only vector in the matrix's nullspace is $\vec0$.
In general, the kernel is not the zero vector, and usually you want to compute it. 
If we have only one solution we could point to the unique solution of our LI columns, so we only have one solution being the zero vector.

The dimension of the subspace containing only zero vector is zero.
That is because the basis of a subspace containing only zero vector is the empty set, and the length of the empty set (definition of dimension) is zero.

The format is we turn it in REF, we write the SLE, then find the constraints that apply for any vector in the kernel.

A matrix being invertible is equivalent to the matrix having kernel zero.


When we get to REF, we say that this matrix is in REF and we want to find the constraints/SLE for vectors such that when multiplied by this matrix we get a zero.

In a case of a kernel longer than the zero vector, we get an SLE with more than one solution. 
Once more, in that case, we solve for the scalar variables in terms of another variable. Then, the constrained vector is in terms of our free variable(s).  Then we pull the scalar variable out of the vector.
In case we only have one vector, we would write that the kernel of the matrix is equal to the span of the vector.
Now, the dimension of the span of that single non-zero vector is 1 (one).

What if we want a basis for our kernel? We want to reduce the list into LI. A list of length 1 is trivially LI. Though, for this technique, where separating the vector by the scalar variables, we are pretty much guaranteed that they are LI, so the basis would literally just be the list.

Now, onto range.
Asking about the image of a matrix, is the exact same as asking about the span of its columns. This is trivial, as we split the matrix and scalar variable vector by matrix linearity into a multiplication of the scalar by each of the matrix' columns. We already know how to remove linearly dependent vectors to achieve a basis.
If we have a column that has no pivot, then we have found a redundant vector corresponding to that column. Then we can remove it and the span will be the same. Then, the span will be the remaining column vectors.

The dimension of a range is the rank.
It is not true that the span is LI. Trivially, the columns span their own span, but to obtain LI the whole pivot idea comes back. We remove the linearly dependent vector for the span and obtain the basis.

An important theorem that relates to this is 
$A \in M_{n,m}(F)$ then it is taking vectors in $F^m$.
Then, the **rank theorem**, otherwise called the **fundamental theorem of linear algebra**.
$$m = dim(ker(A)) + rank(A)$$
If the rank is zero, then the kernel is the entire space.
If the dimension of the kernel is zero, then the image is the entire space.
We could be asked...
"Is there a matrix  $A \in M_{5,7}(R)$ with $dim(ker(A)) = 4$ and $rank(A) = 3$?"
This question is testing if you know what these terms mean and if you know the formula for the rank theorem. In this case we know have $7 = 4 + 3$ which holds. Therefore, it is true.
In this case we wouldn't need to give an example.

With the transpose... Once you understand the the range corresponds to the span of the columns, then the range of the transpose will be the span of the rows. 

Okay, change of basis.
A change of basis matrix is always invertible, it is square, and it is not hard to compute, as we can use equivalences.
The slides are very good for this.

Extension of an LI list is generally not a basis.
First we compute REF, then we start adding things.
We augment it with the standard basis, and apply row operations.

We will definitely have change of basis, 2-3 true or false questions, computing matrix inverse, computing fundamental subspaces, and some questions about how rank relates to the columns.

!!! UPDATE !!!
TRUE OR FALSE QUESTIONS WILL NOT BE IN THE TEST APPARENTLY

<u>Important Theorems:</u>
- Rank theorem
- Equivalences 
	- (kernel of matrix is $\{\vec0\} \iff A$ is invertible)
	- A is invertible $\iff$ it can be reduced to $I_n$
- Relationship between columns structure and fundamental subspaces
	- Span of the columns to the range, then span of rows corresponds to range of transpose.
	- In REF, bottom k-zero rows correspond to the vectors in the transposes' kernel

