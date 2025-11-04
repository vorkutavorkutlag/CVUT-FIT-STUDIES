[[PRACTICE 2]]
## Finite Dimensional Vector Spaces

By definition, a vector space V is called **finite dimensional** if there is a list of vectors in V such that $V = span(v_1, ..., v_n)$
A vector space which is not finite dimension is called **infinite dimensional** 
$F^3$ is a finite dimensional vector space.
For every field $F$, and integer $m$, $F^m$  is a finite dimensional.

A vector subspace of a finite dimensional vector space will always be a finite dimensional vector space.

A list is called linearly independent if the only choice of $c_1 v_1 + ... + c_n v_n = 0$ is when all the scalars are equal to 0.
Observe that if the list is linearly independent and v is in the span, then there are unique scalars such that v will be rewritten in the terms of the vectors.

One can verify the following:
1. Any list of vectors containing zero is not linearly independent. (X is not LI iff we can find scalars such that zero vector can be expressed with scalars and vectors and at least one scalar is not zero)
2. The list (v) is linearly independent if and only if v is non-zero.
3. A list of vectors with length 2 (containing two vectors) is linearly independent if and only if none of them is a scalar multiplication of the other
4. If a vector is removed from a linearly independent list, the remaining list is linearly independent.


#### Comparing the length of spanning sequence and the length of linearly independent sequences
The following result compares the length of linearly independent sequence with a length of a spanning sequence. In a finite dimensional vector space, the length of every linear independent sequence of vectors is less than or equal to the length of every spanning sequence of vectors.
For example, the length of any linearly independent list of vectors in $M_{2,2}(F)$ is at most 4.

Let $(x_1,...,x_n)$ be a sequence of vectors from a vector space $V$ of the length $n \geq 2$. 
Then $(x_1,...,x_n)$ is LD if and only if there exists $1 \leq k \leq n$ such that:
$$span (x_1,...,x_n)=span(x_1,..,x_k-1,..,x_k+1,...,x_n)$$
As in, if one of vectors is a linear combination of the others.


#### Basis
Let V be a vector space over F. A **basis** for V is a list of vectors which is linearly independent and spans V. In other words, a sequence is a basis for V if and only if every vector in V is written uniquely as a linear combination of the vectors.
The idea of basis is that it is "big" enough to span the space but it is not "so big" that it contains redundancies. The last property is captured by being linearly independent.
For a spanning list of vectors, we must have at least one solution in the SLE.
For linear independence, we must have a pivot at every row in the SLE for a unique solution.
