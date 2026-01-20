
The definition of a relation is the subset of the cartesian product of two sets. The difference between that and mapping is, that by definition, a mapping only has at most one y for every x.

The domain of the relation, $D(R)$ $R \subseteq X \times Y$ is defined $\{x \in X : \exists y \in Y : (x, y) \in R\} \subseteq X$ 
The image of the relation, $D(R)$ $R \subseteq X \times Y$ is defined $\{y \in Y : \exists x \in X : (x, y) \in R\} \subseteq Y$ 

We can represent a relation with a diagram of all the elements with arrows from one element to another. Alternatively, can also represent it in a binary matrix, where we look at a row being in relation with the column on the same index.
0 means we have no relation, 1 is when we have a relation.
The arrow from a to b doesn't necessarily mean b is in a relation in a. it means a is in relation with b.

Relations have properties.

**RE**, Reflexivity. for every element in the relation, it is in relation with itself. It can be expressed that the diagonal of our relation matrix is filled with 1's. it can also be expressed by having loops in the diagram (elements referring to themselves).
$\forall x \in X ~:~ xRx$ 
This is identical to saying $\Delta_X \subseteq R$ (the set of $\{(1,1), (2,2), ...\}$ is a subset of our relation)   

**SY**, Symmetry. We say that a relation is symmetric if, for every two elements, if one is in relation with the other, the other is in relation with that one also. In a diagram, it can be represented through all double-ended arrows (no single-way arrows).
$\forall x,y \in X ~:~ xRy \implies yRx$
Also, that is the same to say $R^{-1} = R$ . The inverse of the relation is equal to the relation. Note, that the inverse here would be the **transpose** of the matrix, not its inverse. 
A visual way to look at it is to see if the entries in the binary matrix are symmetrical across the diagonal.
A methodical way to check is to swap around the variables in the equation that is used to define the set. For example, $n+m \leq 6$ becomes $m+n \leq 6$ (symmetric!)

Sidetrack: inverse of relation is the defined as following.
$\forall x,y \in X ~:~ (x,y) \in R \implies (y,x) \in R^{-1}$ 
Basically, the x and y switch places. No relations are "cut off", the arrows just switch sides. If the arrows are double-ended, nothing changes. Also, this is the transpose of the relation matrix.

**TR**, Transitivity. If x is in relation with y, and y is in relation with z, then x is in relation with z. That is equivalent to $R^2 \subseteq R$. If you want to draw, we see "triangles" between every three relations. Analogically, $M^{[2]} \leq M$ 
$\forall x,y,z \in X ~:~ xRy \land yRz \implies xRz$

**AN**, Antisymmetry. If two elements are symmetrical, then they must be the same element. This does not immediately negate SY! 
Equivalent to $R \cap R^{-1} \subseteq \Delta_X$ . 
Graphically, equivalent to the only two-sided arrows being loops.
$\forall x,y \in X ~:~ xRy ^ yRx \implies x = y$  

**AS**, Asymmetry. A stronger antisymmetry. If one element is in relation with the other, the other cannot be in relation with that element! 
$\forall x,y \in X ~:~ xRy \implies \neg yRx$ 
This can also be seen as $R \cap R^{-1} = \emptyset_X$ the empty relation. 

**IR**, Irreflexivity. For every element, it is never in relation with itself.
$\forall x \in X ~:~ \neg xRx$
Equivalently, $R \cap \Delta_X = \emptyset_X$ (The diagonal is filled with zeros) 
Graphically, it means no loops.


The domain of a relation are all the elements **from which** there is an arrow leading.
The image of a relation are all the elements **to which** there is an arrow leading.

When computing the square of a relation, that is, applying the relation twice on every element (kind of like a board game, you go twice), we may find it either by following the arrows on the diagram twice (again, like a board game), or by multiplying the relation matrix. However, then we get numbers bigger than 1... How could this be?
We will not be taking that matrix. We will be taking the matrix where every 0 remains a 0, and every positive element becomes a 1.
When we do the product, we get how many paths we can obtain, but when we want the actual binary relation matrix, we have to clamp the numbers back to 1.

When a condition for the implication is never met (if x then y, so x is never met), then the implication is always true. This is relevant for antisymmetry. If there is no symmetry at all, meaning there is never a condition like $xRy \land yRx$, then $x=y$ doesn't matter - so it is antisymmetric. Also, it is asymmetric, if it has no loops.

The union of two relations is all the arrows in one relation and all the arrows in the other relation. 
The intersection of two relations is only the arrows that appear in both relations.

If two relations are transitive, their union is not necessarily transitive.
If two relations are transitive, their intersection is transitive also.
When given these type of questions, draw simple (maybe 4 element) relations, and do the operations on them. Then, work with the definitions (like $R^2 \subseteq R$) 

An **equivalence relation** is a relation that is **RE, SY, TR** (all the good ones!) at the same time. 
When we have an equivalence relation we may partition the set according to the equivalence class. An equivalence class means that we are clustering all the elements that are in (equivalence) relations with each other into a single element (doesn't matter, since it is equivalent!). The partition is $X/R$ .
The equality sign is an example of an equivalence relation.

A **partial order** relation is a relation that is **RE, AN, TR** (same as equivalence, except antisymmetry instead of symmetry).
The less than or equal to, greater than or equal to signs are examples of partial order relations.
A maximal element is an element that is maximal with all the elements it can be compared with. THE MAXIMUM is an element that is not only a maximal, but it can also be compared with all the elements.
A minimal element is an element that is minimal with all the elements it can be compared with. THE LEAST (MINIMUM) element is an element that is not only a minimal, but it can also be compared with all the elements.
You are not always guaranteed being able to compare two elements.
There can be several maximal and minimal elements, but only a single maximum/minimum element.
![[Pasted image 20260120232232.png]]
![[Pasted image 20260120232341.png]]


Hasse diagram of a partial order relation, we know that we are going to have loops everywhere, so we strip them off. Also, we know that we have transitivity, so why bother writing that? It is a simplified version of the original diagram. We put the maximal element at the top, and lower, we put elements smaller than it. We may have a situation where we have 4 and the top, 3 below it, and then 2 & 1 as siblings, underneath the 3.


Consider the relation $R = \{(a, b), (c, c)\}$ on the set $X = \{a, b, c\}$. Find the smallest (in terms of set cardinality) relation S such that R ⊆ S and S is an equivalence. 
Write the quotient set X/S.

The smallest equivalence relation S is $(\{(a,a),(b,b),(c,c),(a,b),(b,a)\})$. 
The quotient set X/S is $(\{\{a,b\},\{c\}\}) = ( \{ [a], [c] \} )$.
