[[RELATIONS]]
## ...Continuing Relations


While a mapping is also a subset of the cartesian product, it has the limitation of having at most one element in the codomain corresponding to the domain. However, a relation has no such limitation.

You can define the domain and image of a relation as the following.
$D(R) =\{a \in X : \exists b \in Y : (a,b) \in R\} \subseteq X$
$Im(R) = \{b \in Y : \exists a \in X: (a,b) \in R\} \subseteq Y$

It is possible to represent a relation in multiple ways.
By listing all the items, by making a graph of nodes, and a matrix.

In a finite set, we can always do the listing.
Or, we can define properties sometimes when it's available.
Additionally, we can represent the matrix of the relation, where the rows symbolize $a$ and the columns symbolize $b$. We write $1$ where the relation holds, and $0$ where the relation doesn't hold.
It doesn't have to be natural numbers, you are simply indexing them. It can be whatever object it is.

When you have a relation, you can study the properties of it.

It is reflexive if for every element in the set, it is in relation with itself.
Graphically, it means loops everywhere.
It is symmetric, if for every two elements, if $xRy \implies yRx$ 
Graphically, it's two-way arrows.

It is transitive, if for every there elements $xRy \land yRz \implies xRz$
It is antisymmetric when all symmetries are strictly reflexive instances.
$xRy \land yRx \implies x = y$
It is asymmetric when $xRy \implies \neg y R x$ 
Note, asymmetry is an extension of antisymmetry.
It is irreflexive when for every element, it is not in relation with itself.
Note that it is not the negation of the reflexivity, because of the quantifier.


Let us discuss fundamental relations.
The empty relation $\emptyset$.  No one is in relation with itself, the zero matrix.
The diagonal relation $\Delta x$ . Matrix is the identity matrix.
The complete relation $X \times X$ everyone is in relation with everyone. Matrix of all ones.

Reflexivity is telling us our diagonal is all ones.
Symmetry is telling us the matrix is equal to its transpose (symmetric across the diagonal).
Transitivity is telling us $R^2 \subseteq R$  (the truth valuations are a subset)
Antisymmetry is telling us every time we have a one, the mirror across the diagonal is a zero.
Irreflexivity is telling us our diagonal is all zeros.




Let's say we want to apply $R^2$. That we would be applying the composition $R \circ R$
Consider a diagram. If we apply the relation twice, we 'map' for the first time, and then 'map' a second time, and our result is the union of all those results.
The more computational way to compute it is computing the matrix of the relation squared. $M_{R^2}=M_{R \circ R} = M_R * M_R = M_R^2$  
Little problem, we are looking for a binary matrix. But here we receive numbers bigger than one. This is why it's 'almost equal'. Every positive number here is the same as if it were 1, and every 0 stays a 0.
The raw matrix will include how many ways we can reach these places through our relation 'mappings'.


Graphically, the domain is all elements from which arrows point.
Graphically, the image is all elements to which arrows point.

The inverse relation is computed as $xR^{-1}y \iff yRx$ 
It can also be computed by transposing the matrix.

Side-note: if the difference of two numbers is the multiple of $n$, then $a \equiv b \mod n$ 


If we are applying mapping $S \circ R$, we firs apply $R$ then $S$, same with other compositions.
Their matrix will be $M_{S \circ R} = M_R * M_S$ 
Not to be confused with linear algebra. Mind the order.

A union of two transitive relations is not necessarily transitive.
Neither is their composition necessarily transitive.
Though, their intersection is always transitive.

According to theorem, if $R$ is transitive, then $R^n$ is transitive.

Side-note: symmetric means only loops and double arrows. no single arrows.

Let us discuss now equivalence relations.
It is a relation $R$ that is at the same time RE+SY+TR
For example, the equality, inequality, or the logical equivalence, or $\iff$ etc.
Every time we have an equivalence relation, it can be partitioned, clustered together.
When taking that partition set with the quotient of $R$, we can optimize it further by classifying it with only one set.
Then, $[a]_R = \{x \in X: nRx\}$

There exist also partial order relations.
A partial order relation is at the same time RE+AN+TR
For example, the less than or equal to, greater than or equal to.

$a$ is a minimal element when it is always "less than or equal to" (relation) another 
element. It is always on the left of the expression $a \leq b$
However, the least element has to have a relation with all the elements and still be a minimal element.
The maximal element is a maximum element that is greater than or equal to another element. It is always on the right of the expression $a \leq b$
However, the greatest (maximum) element is the maximal element that has a relation with everyone.

For partial order relations we may be drawing the Hasse diagrams instead.
It 'removes' the reflexive elements.
We put the bigger elements at the top, and the smaller elements to the bottom, such that there are no arrows.
It 'removes' the arches of transitivity.

