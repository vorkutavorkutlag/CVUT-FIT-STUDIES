### Introduction

The student should be familiarized with the following topics.
R: real number
n: integer in N={1, 2, ...}

R^2 represents a two dimensional grid of possible vectors. As in:
$$R^2 = \{(x_1, x_2) | x_1, x_2 ∈ R\}$$
(Note, that is supposed to be a vector. Vertical matrix. I don't know how to do that.)

The basis of this ***Vector Space*** is the zero vector, vector addition, and multiplication by scalar. Following that, you may also define subtraction by multiplying by (-1) and then adding. The zero vector is defined by all of its elements being 0.
If you add it to any vector, you get the identity of the vector (i.e. nothing changes). If you multiply it by any scalar, it stays the zero vector.

At the same time, it is possible to define R^3, following the same suite. We can define any dimension of R, R^n {n ∈ N}. 

#### Properties of Vectors

Commutativity: v_1 + v_2 = v_2 + v_1
Associativity: (v_1 + v_2) + v_3 = v_1 + (v_2 + v_3)
Associativity: c_1 \* (c_2 \* v) = (c_1 * c_2) \* v
Distributivity:  c*(v_1+v_2) = cv_1 + cv_2
Distributivity: (c_1+c_2) \* v = c_1 \* v + c_2\*v
Multiplication by 1: 1 \* v = v
Existence of zero vector: 0^ + v = v + 0^ = v



F^n (F: Field, R | C, Z_p: (prime numbers)) -> vector spaces.
Now, to look at their "linear structures". 
- Linear combinations of vectors
R^n: v_1, v,2... To create more vectors, we can combine the vectors, or multiply them by scalars with the requirement that c_1, c_2 ∈ R

Definition: Let v_1, ..., v_m ∈ R^n and c_1, ...c_m ∈ R.
Then, c_1 \* v_1 +...+ c_m \* v_m is called a linear combination of vectors v1,...,v_m.
The set of all linear combinations of v_1, ..., v_m is called a linear span of v_1, ..., v_m.

It is denoted by Span(v_1, ..., v_m) or $$<v_1, ..., v_m>.$$
For example, v = (1, 1) ∈ R^2 -> line in R^2 <0>  [=(0, 0)] and contains (1, 1)
passing span(v) = {c * (1, 1) | c ∈ R} = {(c, c) | c ∈ R} = R.
Meaning, the span of (v) is R.

In the case that we have two vectors, v_1 and v_2, their span, which can be calculated in the same manner, will sum up to be $$\{(c_1, c_2) | c_1, c_2 ∈ R\} = R^2$$

The following is a common task in the course.
In R^n given vectors v_1, v_2, v_3... v_m
If v ∈ R^n is given. Decide if v ∈ Span(v_1, v_2, v_3, ..., v_m).
Determine explicitly the set of all linear combinations of v_1, v_2, v_3, ..., v_m (i.e. span(v_1, v_2, v_3, ..., v_m))

To solve this, the following is required.

##### System of Linear Equations (SLE)
##### Gaussian Elimination Method -> Solves SLE

A simple example for SLE:

x + y = 10
-x + y + 12 = -1

Except, we will be tackling n equations with n variables. And so, we must systemise it.

Given two vectors:
v_1 = (-1, 2) and v_2 = (2, -4)
span(v_1, v_2) = $$\{c_1 * (-1, 2) + c_2 * (2, -4) | c_1, c_2 ∈ R\}$$
=$$\{(-c_1 + 2c_2, 2c_1 - 4c_2) | c_1, c_2 ∈ R\}$$
this simplifies into =R. Even though we have two vectors, the span is only a single dimension, since these two vectors are on the same 'line' on a graph. 

Similarly, in any R^n set of vectors there are n possibilities for the span. It may be either the same amount of dimensions (n), two vectors may be sharing a line so one dimension less (n-1)... all the way to all the vectors sharing a line, so one (1) dimension.  
##### Linear Independence
Linear independence is defined by the set of two vectors having a two dimensional span. Likewise, vectors in R^n, if they result in a span of n dimensions (=R^n), then all the vectors are linearly independent from each other. If two or more vectors result in a single dimensional span, they are linearly dependent on each other.


##### Matrices
To solve SLE, one must convert them to matrices.

A matrix is a rectangular two dimensional array of items represented by rows (left and right) and columns (up and down). It can be used to represent an array/list of vectors.
Matrices can be associated with 4 vector spaces
A =
1, 2, -3
2, 0, 0

A ∈ M(R)
(1, 2) -> first row second column entry = a\_12 = \[A\]\_12

Given two matrices A, B, given A and B have the same dimensions, you may do operations on them, such as addition. You add every respective entry to each other, matching them according to their indices.
Likewise, you may define scalar multiplication. 
c ∈ R, A ∈ M_m,n (R). 
c \* A = ca_11, ca_12, ...
		...., ..., ...

A zero matrix is defined as a matrix wherein all of its entries are zero, notated as `0_m,n`.

***The Determinant*** is a scalar-valued function of the entries of a square matrix. The determinant of a matrix A is commonly denoted det, det A, or |A|. Its value characterizes some properties of the matrix and the linear map represented, on a given basis, by the matrix. You may only use methods of computation discussed in the course

For a square matrix, an ***eigenvector*** is a non-zero vector that, when multiplied by the matrix, only changes in length (stretches or shrinks) but not direction. The factor by which it changes is the ***eigenvalue***, a scalar that can be positive, negative, or zero. You find eigenvalues by solving the characteristic equation det(A - λI) = 0, where A is the matrix, λ is the eigenvalue, and I is the identity matrix. Eigenvectors are then found by solving the equation (A - λI)v = 0 for each corresponding eigenvalue λ

Diagonalizability of matrices... To be continued