[[COURSES/BIE-LA1/LECTURE 8 (Tutorial)|LECTURE 8 (Tutorial)]]
Linear Algebra practice with Christian Hughes and David Lapunik on Fridays starting 24.10.2025
18:00-19:30 in JP6:571
Every week before the test, there will be an available practice test in the Friday practice
Christian: hughechr@cvut.cz
David: lapunndav@cvut.cz
## Vector Spaces and Related Terms

Last lectures, we have talked about structures of fields ($R$, $Z_p$, $C$), such as $F^n$
We have vector addition $F^n + F^n \rightarrow F^n$, scalar multiplication $F * F^n \rightarrow F^n$
We have the following properties:
![[Pasted image 20251023111122.png]]

Vector spaces is the generalization of $F^n$, we may do with them linear combinations and linear independence. It includes but is not limited to all properties of $F^n$.

Let F be a field. A vector space over F is a set V equipped with two operations, vector addition and scalar multiplication such that commutativity, associativity additive identity, additive inverse, multiplicative identity, multiplication associativity hold for any vector and scalar.

The two distributive properties which connect scalar multiplication and addition:
$a * (u+v) = a * u + a * v$
$(a+b) * v = a * v + b * v$

Elements of V are called V, elements of F are called scalars.

$M_{m,n} (F) \implies$ vector space over F.
Need to introduce vector addition and scalar multiplication.
We have the vector addition with matrix addition - addition each component to its respective index in the second matrix.
We have the scalar multiplication by multiplying every element of the matrix by the scalar.
We have the zero of the field by setting all the elements to be equal to zero.
The additive inverse for each matrix respectively is the matrix of equal dimensions with all the signs flipped such that $M_a + M_b = \vec0$ 

This is a non-trivial vector space. Another example with mapping:
Given the set V = {f : R -> R | f is mapping/function}
then V is a vector space over R. 
Essentially we do the function over each one of the elements.

##### Theorem
Let V be a vector space over a field F. Then the following holds:
1. There exists exactly one zero vector $\vec0 \in V$
2. For all $\alpha \in F$  we have $\alpha * \vec0 = \vec0$
3. For all $v \in V$ we have $v + \vec0$ = v
4. For all $v \in V$ there exists $w \in V$ such that $v + w = \vec0$. i.e. there exists unique **additive inverse**. We will denote $w$ by $-v$.
Proof
Follows directly from the axioms of vector space and field properties, however, we postpone it to the second course in linear algebra. If you may prove it, you may receive extra points. \^\_\^ 

#### Subspaces
A subspace of a vector space over F is a nonempty $S \subseteq V$ satisfying the following properties:
a. For any $v, w \in S, v + w \in S$ (that is S is closed under vector addition)
b. For any $v \in V$ and $\alpha \in F, \alpha * V \in S$ (that is S is closed under scalar multiplication)
Then write $S \subset \subset V$

Remark: Observe that property (i) implies that subspaces are flat and property (b) makes it so that they are infinitely long (just like lines and planes).
Subspaces do not have any holes or edges, and if they extend even a little bit in any given direction, then they must extend forever in that direction.

In a more geometrical example, given two vectors on the same plane, there does not exist any way to add them such that they will extend to a 'foreign' plane (2nd dimension vectors cannot create 3rd dimension vector). Therefore, it is considered a subspace.


Let U be a subspace of V. Then:
1. the zero vector $\vec0$ of $V$ is in $U$;
2. for any vector $u \in U$ the addition inverse $-u$ is in $U$.
Let S be a subspace of vector space V. Then S is a vector space with the same addition and scalar multiplication of V.

The above corollary provided us plenty of examples of vector spaces.

The definition has the minimum of the assumptions.
$U \subseteq V$ if:
1. $\forall v, w \in U \implies v + w \in U$ USES VECTOR ADDITION FROM V
2. $\forall u \in U, \forall \alpha \in F \implies \alpha * u \in U$ USES SCALAR MULTIPLICATION FROM V


if $U \subseteq V$ does not contain $\vec0$ then $U$ cannot be a subspace. 

Question: V: vector space on $F$, $S \subseteq V$ subset.
Is $S$ a subspace of $V$?
To answer this:
Is $\vec0$ in $S$? 
No - $S$ is not a subspace.
Yes - Is S closed under scalar multiplication? (result belongs to S)
No - $S$ is not a subspace.
Yes - Is S closed under vector addition? (result belongs to S)
No - $S$ is not a subspace
Yes - $S$ is a subspace.

Of course you may switch the order of the scalar multiplication and vector addition checks. It is simply important to remember that it must satisfy all of them.

The test will include tasks to prove if a subset is a subspace or not a subspace.

If V is a vector space, and if S is a subspace, then S is a vector space as well.
We check those by the restrictions of vector addition and scalar multiplication.
S can be a subset and a vector space, and still not be a subspace.

