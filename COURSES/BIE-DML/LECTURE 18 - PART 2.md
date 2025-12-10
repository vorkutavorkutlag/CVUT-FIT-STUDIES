[[LECTURE 19 (TUTORIAL)]]
# Relations

Relation is a relationship between objects. We see relations all around us, their properties are interesting for mathematics. We already know from predicate logic some relations. Its interpretation for elements of specifics sets are relations.
Some relations to consider.
Irma knows Arman (Irma, Arman) $\in$ knows
123456789 is divisible by 643 (643, 123456789) $\in$ divides
Numbers 3,4,5 satisfy $3^2+4^2=5^2$ (3,4,5) $\in$ Pyth

A binary relation is defined as such.
Let $X,Y$ be some nonempty sets, and let $R \subseteq X \times Y$ be an arbitrary mapping.
Except, it isn't really a mapping. Mappings say that for every $x$ there is at most one $y$.
However, there could be a lot more than one $y$ for every $x$.
The ordered triple $(R, X, Y)$ is called a binary relation from X into Y. We call X the left domain and Y the right domain of the relation $(R, X, Y)$.

If $(a,b) \in R$ we say that $a$ is in relation $R$ with $b$ and we write $aRb$
If $(a,b) \not \in R$ we say that $a$ is not in relation $R$ with b and we write $\neg (aRb)$
A binary relation $(R, X, X)$ is called a binary relation on set $X$.

$n$-ary relations are subsets of cartesian products of $n$ non-empty sets, but in this course we will only be interested in binary relations.

We can represent a relation using a set, matrix, or diagram.
This ties in to the fact that mappings are sets, matrices.
![[Pasted image 20251209152852.png]]

These representations work well for finite relations.
Then, what do we do with infinite relations?
We cannot list all its elements, or draw infinite matrices or diagrams, so we are left with using the characterizing properties and predicate logic with relations.

Let us define the domain and range of a relation.
$$D(R) := \{x \in X: (\exists y \in Y) xRy\} \subseteq X$$ $$Im(R) := \{y \in Y: (\exists x \in X) xRy\} \subseteq Y$$
We can always inverse a relation. The inverse of a relation is the relation $(R^{-1}, Y, X)$
The inverse of $(R, X, Y)$ always exists.
$$R^{-1} := \{(y, x) \in Y \times X: (x,y) \in R\}$$
The inverse of a relation is its transpose.

We may also compose relations. Let $(R, X, Y), (S, X, Y)$ be some binary relations. 
$(R \circ S, X, Z)$ is defined by $$x(R \circ S)z \iff (\exists y \in Y) (xSy \land yRz)$$ Is called the composition of relations $R$ and $S$.
Then, the matrix composition:
![[Pasted image 20251209155447.png]]
