
This does not correspond to any lecture, tutorial, or TA practice session in particular.
What follows is a collection of personal notes, ramblings, and similar useful information that we will need to memorize and feel comfortable with using for the upcoming test.
Most of the accent will be put on theorems that we (and cannot!) use.
Primarily, pay attention to the theorems that were added after the first test.
Still, we will be first reviewing some things we have already learnt to cover the entire lecture in its entire context.
Proofs, examples, and other topics will be 'ignored' for the most part.

Be warned - this part contain a big number of repetition.
If you are confident in your Test 1 knowledge, you can skip to the end of this to read about bases and dimension, coordinates w.r.t basis.
Then, of course, continue reading to Part II.
[[TEST 2 PREPARATION - CHAPTER II]]

# CHAPTER I: Vector Spaces, Linear Span, Linear (In)dependence, Bases and Dimension, Coordinates w.r.t Basis

# <u>Vector Spaces</u>

So, this sort of leaks into the territory of the previous test, but we will be using these theorems to define the upcoming theorems, so it's good to refresh our memory a bit.

First of all, let us remind ourselves that a vector space over F is a set V equipped with two operations. Vector addition, scalar multiplication, such th they are commutative, associative, have additive identity, additive inverse, multiplicative identity, and multiplicative associativity.

<small>We will be denoting a lot of theorems. The order here is arbitrary, and you shouldn't remember it by heart, obviously. I am simply numbering them so that we can refer to them again in the future more easily.</small>
### Vector Space Theorem (#1)
Let $V$ be a vector space over field $F$. Then the following holds:
- There is exactly one zero vector $\vec0 \in V$
- For all $\alpha \in F$, we have $\alpha * \vec0 = \vec0$
- For all $v \in F$, we have $v + \vec0 = v$
- For all $v \in V$, there exists unique $w \in V$, such that $v+w=\vec0$.
The proof is derived from axioms of vector space.

Then, once we have the definition for a vector space, let us refer to the subspace.
A subspace of a vector space V over F is a nonempty subset $S \subseteq V$ satisfying the following properties:
- Closure under vector addition: For any $v, w \in S$  it holds that  $v + w \in S$ 
- Closure under scalar multiplication: For any $v \in V, \alpha \in F$ it  it holds that $\alpha v \in S$
Then we write $S \subset \subset V$ 

For example, in $R^2$, all non-trivial subspaces are lines containing $\vec0$ in $R^2$. 
A common misconception is that $R$ is a subspace of $R^2$. It is not

#### Proposition & Corollary
Let $U \subset \subset V$. Then:
- The zero vector $\vec0$ of $V$ is in $U$
- For any vector $u \in U$, the additive inverse $-u$ is in $U$.
Let $S \subset \subset V$. Then S is a vector space with the same addition, scalar multiplication of V.

$\{\vec0\}$ and $V$  are the trivial subspaces of V.
Subspaces P, where $P \neq V \land P \neq \{\vec0\}$  are called proper subspaces.
$0 \not \in P \implies P$ is not a subspace of V.
$P \subseteq V \land \vec0 \in P$ are not sufficient conditions for $P \subset \subset V$. (Must prove closures)

Author's note: Be careful when determining whether a given set of vectors is a subspace or not. In the last test, the professor pulled a trick stating $B_1^2 + |B_4| = 0$  as one of the 'conditions' for the subset. It may look innocent at first, and many made a mistake saying it is not closed under scalar multiplication due to the non-linearity of $B_1$. However, this expression is algebraically equivalent to $B_1 = B_4 = 0$, as the sum of a square and absolute value is equivalent to zero if and only if they are both zero (as none of them can be negative). Then, with that consideration, we see that it is indeed closed under vector addition and scalar multiplication.
TL;DR: Pay attention to any 'gotchas' while evaluating vector spaces.

# <u>Linear Span</u>

This overlaps a lot with the previous topics of span, but the main difference here is the relation between the span and subspaces.
Let us recall that the span of any vector list is the set of all linear combinations of those vectors. That is, $span(v_1,...,v_p) = \{c_1v_1+...+c_pv_p | c_1...c_p \in F\}$ for the vectors in vector space $V$ over $F$.

### Linear Span Theorem (#1)
Suppose that vectors $v_1,...,v_p$ are vectors in vector space $V$. Then their span is a subspace of V. Indeed, the span of the vector list is the smallest subspace of V containing the vectors.
$span(v_1,...,v_p) \subset \subset V$

### Linear Span Theorem (#2)
Let $B$ be a vector space over field $F$ and $M \subseteq V$ be a set of vectors. The span of $B$, denoted by $span(B)$ is the set of all finite linear combinations of vectors from B.
If $M \subseteq V$ then $span(M)$ is a subspace of $V$. 
Indeed, $span(M)$ is the smallest subspace of V containing $M$.

These two theorems go together, and are different pronunciations of the same statement...

Now let us discuss spanning sequences/sets.
Let $V$ be a vector space and $\chi$  be a list of vectors in $V$ such that $span(\chi) = V$.
Then we say that $V$ is spanned by $\chi$, $\chi$ spans $V$, $\chi$ is a spanning list or sequence of $V$.
It is reasonable to search for the "smallest" spanning set or sequence, that being the basis.

## Linear Span Theorem (#3) {IMPORTANT} 
Let $F$ be a field, let $v1,..,v_n$ be vectors in $F^m$ and $b \in F^m$.
Let $A \in M_{m,n}(F)$ with columns $v1,...,v_n$.
Then, $V = span(v_1,...,v_n)$, as in, the vectors span $V$...
if and only if the REF form of $A$ has a pivot in every row.


Finally, let's discuss finite dimensional vector spaces.
A vector space $V$ is called finite dimensional if there is a list of vectors $(v_1,...,v_n) \in V$ such that $V=span(v_1,...,v_n)$. A vector space which is not finite dimensional is called finite dimensional.
An infinite dimensional vector space has no list of vectors that spans it, as there will always be another vector we could possibly to increase the span. You cannot 'catch up' to infinity.
### Linear Span Theorem (#4)
Every subspace of a finite dimensional vector space is finite dimensional.


# <u>Linear (In)dependence</u>

Once more, this is a topic the student should have known for the first test, so we will only be skimming over it.

The definition of sequence of vectors is as follows.
Let $V$ be a vector space. By the term sequence of vectors of length $n \in N$, we understand the ordered n-tuple $(x_1,x_2,...,x_n)$ of vectors from $V$.

Then, linear independence is defined as follows.
A list $(v_1, ..., v_n)$ is called linearly independent (LI) if the only choice of $c_1,...,c_n \in F$ that makes the linear combination $c_1v_1 + ... + c_nv_n = \vec0$ is $c_1=...=c_n=0$
Observe that if a list is linearly independent and some vector is in the span of that list, there exist unique scalars to represent that vector as a linear combination of the other vectors in that list.

One can verify the following:
- Any list of vectors containing a zero vector is not linearly dependent.
- The list is linearly dependent if and only if v is non-zero
- A list of vectors with length 2 is linearly independent if and only if none of them are scalar multiplications of the other one
- If a vector is removed from a linearly independent list, the remaining list is linearly independent.

Let us now define the counter to this, linear dependence.
Let $V$ be a vector space over $F$. Let $(v_1, ..., v_n)$ be a sequence of vectors from $V$.
The sequence is linearly dependent (LD),
if and only if it is not linearly dependent, i..e. if there exists a non-trivial linear combination of the sequences equal to the zero vector $\vec0 \in V$.
Thus, a sequence of vectors is LD if and only if there exist scalars such that with: $$c_1v_1+...+c_nv_n = \vec0$$ At least one of the scalars is not zero.

One can verify the following:
- A sequence containing two identical vectors is LD.
- A sequence containing the zero vector is LD.
- A sequence of length 1 is LD $\iff$ that vector is the zero vector.
- A sequence of length 2 is LD $\iff$ the two vectors are scalar multiples of one another.
- Adding a vector to an LD sequence results in an LD sequence.


The most straight-forward way to check for linear (in)dependence is the transform the matrix whose columns compose vectors from the vector list into REF using GEM. Then we look at how many solutions there are for the SLE $Ax=\vec0$  Where $A$ is the matrix of our vector list, $x$ are the scalars. If there is only one solution, i.e. where the scalars are equal to zero, the sequence is LI. If there exists more than one solution, the sequence is LD.

The definition of linear independence captures this idea that a redundancy among vectors or linear equations can be identified by whether or not some linear combinations of them equals zero.

### Linear Independence Theorem (#1)
In a finite dimensional vector space, the length of every linear independent sequence of vectors is less than or equal to the length of every spanning sequence of vectors.
That is, for a vector space over $F^m$, any LI list's length $\leq m$ 

### Linear Independence Theorem (#2)
Let $(x_1,...,x_n)$ be a sequence of vectors from a vector space $V$ of the length $n \geq 2$ 
Then $(x_1,...,x_n$ is LD $\iff$ there exists $1 \leq k \leq n$ such that $$span(x_1...,x_n) = span(x_1,...,x_{k-1},x_{k+1},...,x_n)$$
Notice that we skip the $x_k$ vector.
In simple words, it is LD if one of the vectors is a linear combination (LC) of the others.

A related pair of corollaries:
Let $(x_1,...,x_n)$ be a LI sequence of vectors from $V$. Let $y \in V$ such that $y \not \in (x_1,...,x_n)$.
Then, the sequence $(x_1,...,x_n, y)$ is LI.

Also, any LD sequence can be reduced to an LI sequence by removing some vectors without changing the span. {IMPORTANT}


# <u>Bases and Dimensions</u>

Let us define what a basis is.
Let $V$ be a vector space over $F$. A basis for $V$ is a list of vectors which is linearly independent and spans $V$.
In other words, a sequence of vectors is a basis for $V$ $\iff$ every vector in $V$ is written uniquely as a linear combination of the vectors in the sequence.

The idea behind this definition is that the basis is long enough to span the space, but it isn't so long that it contains redundancies. The latter is captured by being LI

### Basis Theorem (#1)
Every spanning sequence of vectors can be reduced to a basis of the vector space.
If $V$ is finite dimensional, then by the definition, it has a spanning sequence $\beta$ .
By the above theorem, the spanning sequence $\beta$ can be reduced to a basis for $V$.
Every finite dimensional vector space admits a basis.

Now let us define what a standard basis for any field be.
Let $F$ be a field with neutral elements denoted by 0 and 1.
The sequence $\epsilon_n = (e_1,...,e_n)$ where $$e1 := \begin{bmatrix}1 \\ 0\\...\\0\end{bmatrix},...,e_n := \begin{bmatrix}0\\...\\0\\1\end{bmatrix}$$
...is a basis of $F^n$ 
Similarly, the sequence $\epsilon = (E_11, ..., E_1n, E_21,..., E_2n, ..., E_m1,..., E_mn)$ where $E_{ij}$ has 1 on the ij-th position and 0 elsewhere is a basis of $M_{m,n}(F)$
The above mentioned basis are standard basis for vectors and matrices.

### Basis Theorem (#2)
This theorem can be considered in some sense a dual of the theorem which says that every spanning list can be reduced to a basis for a finite dimensional space. Here, the other side of the coin.
Every linearly independent list in a finite dimensional vector space can be extended to a basis of the vector space.

Note that the above theorem provides proof for the previous corollary. To see this, choose a non-zero vector in a finite dimensional vector space. Then, the list is linearly independent, so if it is not a basis, it can be extended to a basis of V.

Now, in order to find a basis for the span of a list of vectors...
Suppose that $\chi = (v_1,...,v_n)$ is a list of vectors in $F^m$. Then $S =span(\chi)$ is a subspace of $F^m$.
Thus, $S$ is itself a finite dimensional vector space.
First, we form the matrix $A \in M_{m,n}(F)$ such that $A_j = v_j$ for all $j = (1,...,n)$
Then we apply GEM to obtain REF of $A$, denoted by $A_e$

#### {Important detail}
Finally, the vectors corresponding to **pivot columns** form a basis for $S = span(\chi)$ 

### Basis Theorem (#3)
Let $\chi = (x_1,...,x_n)$ and $\upsilon = (y_1,...,y_m)$ be two finite bases of vector space $V$.
Then, $n=m$. In simpler words, all bases of the vector space $V$ are of the same length.
We may prove this by using previous theorems.
Since $\chi$ is LI and $\upsilon$ is spanning, $|\chi| \leq |\upsilon|$
Since $\upsilon$ is LI and $\chi$ is spanning, $|\upsilon|\leq|\chi|$
Then, we get that $|\chi|=|\upsilon|$

Now let us move onto dimensions.
Let $V$ be a finite dimensional vector space over field $F$. Then the dimension of $V$ is defined to be the length of any basis of $V$, denoted by $dim(V)$. There really is no catch here, even though 'dimension' sounds like this complicated idea that could have more depth.
For the intents and purposes of LA1, it really is jut the length of any basis of $V$.

The one catch is, and this will be important when discussing the null space (kernel), is that the dimension of a vector space consisting only of the zero vector is zero, as its basis is the empty set. Formally, for matrix $A$ whose columns form a list of LI vectors, $ker(A) = \{\vec0\}$.
Then, the basis for $ker(A)$ is the empty set $\emptyset$. (This is standard for zero vector space)
Thus, the dimension of ${\vec0}$ will always be 0 (zero).
Will expand on this later. Back to the topic.

We have two corollaries.
Let $n, m, k \in N$ such that $n$ is the length of an LI sequence, $k$ is the length of a spanning sequence, and $m$ is the dimension of the field $F^m$.
Then we have that: $n \leq m \leq k$

### Basis Theorem (#4)
Let $V$ be a finite dimensional vector space and $P$ be a subspace of $V$  $P \subset \subset V$.
Then, $P$ is finite dimensional and $$dim(P) \leq dim(V)$$ Furthermore, $dim(P) = dim(V) \iff P = V$

### Basis Theorem (#5)
Suppose that $U$ is a subspace of vector space $V$ with $dim(U) = k$. Let $\beta$ be a list of vectors in $U$ with length $k$ then the following are equivalent:
- $\beta$ is a basis for $U$.
- $\beta$ is LI.
- $\beta$ spans $U$.
The above theorem says that to check that a list of vectors whose length is equal to the dimension of the space it is sufficient to verify jut one of these conditions.

__Corollary about equality of two vector spaces__ 
Let $(x_1,...,x_n)$ and $(y_1,...,y_m)$ be two sequences of vectors from $V$. Then $$span(x_1,...,x_n) = span(y_1,...,y_m)$$ $$\iff$$ $$dim(span(x_1,...,x_n))=dim(span(y_1,...,y_m)) = dim(span(x_1,...,x_n,y_1,...,y_m))$$
Note here that if the spans are the same, then the basis of the span of the merged sequence of vectors will be the same as the other bases. This is due to the fact that the basis would get rid of the duplicate, redundancies, and we'd be left with the other basis


# <u>Coordinates w.r.t. Basis</u>
Basis have that name for a reason.
Time to find out why they are the bases of our vector spaces!
Essentially, every vector can be built from the basis in a unique way.

### Coordinate Theorem (#1)
Let $\chi = (v_1,...,v_n)$ be a basis for $V$. Then for each $w \in V$ there exists a unique set of scalars $\begin{bmatrix}a_1 \\ ... \\ a_n\end{bmatrix}$in $F^n$ such that $$w=\sum_{j=1}^na_jv_j$$
This is another way of writing the linear combination for $w$ consisting of the vectors in $\chi$.
Since $\chi$ is spanning, we can achieve every vector in $F^n$.
Since $\chi$ is LI, there is only one solution per SLE, so there is a unique solution for the scalars.
Thus, a unique way to represent every vector using our basis.

Let us now define coordinates.
Once more, given a basis for a vector space, and another vector in that vector space given by the linear combination of the vectors in the basis:
- $a_i \in F$ is called the i-th coordinate of the vector with respect to the basis.
- By coordinates of $w$ w.r.t basis $\chi$ we understand the n-tuple $$[w]_\chi = \begin{bmatrix}a_1 \\ ... \\ a_n\end{bmatrix} \in F^n$$
In simpler terms, the coordinates of any vector are the scalars that we need to use with the basis to achieve the linear combination that is equal to that vector.

### Coordinate Theorem (#2)
This theorem defines some properties for the coordinates.
Let $\beta = (v_1,...,v_n)$ be a basis of finite dimensional vector space $V$. Then:
- For all $v, w \in V$ it holds $[v+w]_\beta = [v]_\beta + [w]_\beta$
- For all $v \in V$ and scalar $a$ it holds $[av]_\beta = a[v]_\beta$

Again, important, to find the coordinates with respect to (w.r.t.) a basis, we need to find the scalars satisfying that the linear combination of the basis' vectors is equal to the vector we want to find.
We turn it into an SLE, which we solve with GEM. There will be exactly one solution since we are working with a basis of $F^n$. Then, the solutions we got are the scalars that when inserted into the linear combination (LC) will achieve the desired vector, and they will be the coordinates with respect to the basis.
The simplest example is with standard basis. Any vector in the vector space will have the coordinates with respect to the standard basis equivalent to its original values.
This can be viewed through the lens of matrix multiplication $\beta x = v$ . If it is the standard basis, then the augmented matrix of that standard basis will be the identity matrix. Then, we see $x = v$, thus the coordinates w.r.t. $\beta$ will be simply $v$ (the original vector).
