[[LECTURE 3 (TUTORIAL)]]
## Linear Combinations
=========================
One of our tasks in linear algebra is to start with given vectors v_1,...,v_k and scalars c_1,...,c_k then use vector addition and scalar multiplication to construct a new vector. In the following we give a name to this process
#### Definition
===========
A linear combination of vectors v_1,...,v_k in F^n is any vector of the form
$$c_1v_1+...+...c_kv_k$$
for some c_1,...,c_k belonging to F.

Let vectors v_1,...,v_m in F^n be given. Then the set of all linear combinations of vectors v_1,..,v_m is denoted by span(v_1,...,v_m). In particular,
$$span(v_1,...,v_m) =\{c_1 *v_1 + c_m*v_m | c_1,...,c_m ∈ F\}$$
Sometimes, we use the notation <v_1,...,v_M> in place of span.
In this course, we will argue to understand properties of the span of given vectors, and to decide if a given vector is in the span of other vectors.
//

In order to tackle the problems of systemising solving the span for multiple dimensions and multiple vectors, we may rewrite it as matrix multiplication.
Key fact: to express a linear combination of given vectors - use matrix multiplication.

Multiplying matrix A with a vector x, we are left with
$$Ax = x_1A_1 + x_2A_2$$
where in x_1 and x_2 are scalars (individual values of vector's dimensions), 
and A_1 and A_2 are vectors (individual columns of the matrix).
therefore, we have a linear combination. In a similar way, we can rewrite a linear combination as matrix multiplication.
$$c_1v_2 + c_2+v_2 = V*[c_1, c_2]$$
	(Wrong LaTeX. essentially, define a new matrix with the vectors and define a new vector with the scalars).



Ax=b is a system of linear equations (SLE). 
A linear equation in n variables (or n unknowns) x_1,...,x_n is an equation that can be written as
$$a_1x_1+...+x_nx_n=b$$
where a_1,...,a_n, b ∈ F are constants called the coefficients of the linear equations.
for example, x_1 + 2x_2 = 1 is a linear equation in R^2.
it can also be re-represented as x_1=  -2x_2 + 1, a two dimensional function with infinitely many solutions. With more variables, it becomes a function with more dimensions.

Oftentimes, we want to solve multiple linear equations at teh same time. That is, we want to find values for the variables x_1,...,x_n such that multiple different linear equations are all satisfied simultaneously. This leads us naturally to consider SLE.

##### Definition
=======
A system of linear equations (or linear system) with coefficients in F is a finite set of linear equations with the same variables x_1,...,x_n. In other words, a linear system of m equations and n variables (or n unknowns) is of the form:
[PICTURE LATER]

Where a_i, b_i ∈ F for i=1,..,m and j=1,...,n..

#### Solution
=======

The solution of SLE is the intersection of all the solutions of the linear equations. It is possible to achieve infinite solutions, finite solutions, and no solutions at all.

Every SLE can be written as a matrix equation in the form Ax=b, wherein A is a coefficient matrix and b is the vector of the equations' solutions. you then make an augmented matrix by adding the b vector as the final row to the coefficient matrix. Usually there is a vertical line separating the coefficients and equation solutions.

There is a systematic way to solve SLE, this method is called Gaussian Elimination, or Row Reduction.
In this method, we apply some operations on rows of the augmented matrix of a system of equations to obtain a simpler form, called echelon form.
The latter matrix is associated to a system of equations has the same set of solutions as the first one, however, it is easier to solve it.
$$(A|b) \rightarrow row-operations \rightarrow (A_e|b)$$
Such that new set of solutions is equivalent to the set of solutions of Ax=b.

If SLE has a "triangular form", then solving it is fairly intuitive. For example,
$$x_1 + 3x_2 - 2x_3 = 5$$
$$2x_2 - 6x_3 = 4$$
$$3x_3=6$$
You can solve the variables one by one.
TO show is at an augment matrix:
