[[COURSES/BIE-DML/LECTURE 21 (TUTORIAL)]]
Finishing up binary relations.
Binary relations are three-tuples of two nonempty sets, and a mapping, which is a subset of the cartesian product of those two sets.

### Relation Composition

For given binary relations $(R, Y, Z)$ and $(S, X, Y)$, the composition of the relations 
$(R \circ S, X, Z)$ is defined as following.
$x (R \circ S) z \iff (\exists y \in Y)(xSy \land yRz)$
It is nearly analogous to mapping composition.

It is not commutative, but it is always associative.

By theorem, regarding composition and inverse of relations.

![[Pasted image 20251216145605.png]]

Let us now focus on dimensions on one nonempty set $X$.
The empty relation will be the empty set; $O_X:=\emptyset$
The identity relation, the diagonal: $\Delta x := \{(x,x) : x \in X\}$  
The total relation will be the total cartesian product; $X \times X$

This can be viewed very simply as matrices. Zero matrix, identity matrix, etc. 

If we compose any relation with the empty relation, we get the empty relation.
If we get any relation with the identity relation, we get the original relation.

Let us discuss about the properties of binary relations on the same set $X$.
Let $R \subseteq X \times X$ be a relation. We define the following properties.
- (RE) reflexivity $(\forall x \in X) (xRx) \iff \Delta x \subseteq R$ 
- Every object is in the relation with itself
- (SY) symmetry $(\forall x,y \in X) (xRy \implies yRx) \iff R^{-1} = R$ 
- If two objects are in a relation in one direction, also are in relation other direction.
- (TR) transitivity $(\forall x, y, z \in X)((xRy \land yRz) \implies xRz) \iff R \circ R \subseteq R$  
- Self explanatory transitivity...
- (AN) antisymmetry $(\forall x,y \in X)((xRy \land rYx) \implies x = y) \iff R \cap R^{-1} \subseteq \Delta x$   
- If they are symmetric, then they are the same.
- (AS) asymmetry $(\forall x,y \in X)(xRy \implies \neg(yRx) \iff R \cap R^{-1} = O_X$ 
- It is antisymmetric, and there cannot be any loops. Stronger antisymmetry. 
- (IR) irreflexivity $(\forall x \in X) (\neg(xRx)) \iff R \cap \Delta x = O_X$ 

Be careful! IR and RE are **NOT** negations of one another. $IR \not \equiv RE$  
Similarly, symmetry and antisymmetry/assymmetry. None of these properties are redundant, none of these are negations of one another. We can see this very easily due to the quantifiers. The quantifiers are never negated.

Any relation that is a subset of the diagonal relation is symmetric **and** antisymmetric at the same time

To disprove any of these, we will need to show that **there exists**  an element such that the formula is negated. i.e. counterexample


If we have some relation $R$ on set $X$ that does not have some properties, we can either add or remove some pairs such that the result will have the desired properties. Using the minimal amount of needed pairs is taking a closure.

Let us use composition of relations to denote integer powers of a relation. $$R^n := $$ $$\Delta x ~~~( n = 0)$$ $$R \circ R \circ ...\circ R ~ ~ (n > 0)$$ $$(R^{-n})^{-1} = (R^{-1})^{-n} ~~~ (n < 0)$$
$R^+$ is the smallest transitive relation containing $R$.
$R^*$ is the smallest transitive and reflexive relation containing $R$
$R \cup \Delta x$ is the smallest reflexive relation containing $R$.
$R \cup R^{-1}$ is the smallest symmetric relation containing $R$
$R \setminus \Delta x$ is the greatest reflexive relation contained in $R$.

![[Pasted image 20251216150256.png]]


Let us move onto two special, significant types of binary relations on set $X$.
That being equivalence relations and partial order relations.

The equivalence relation, informally, is a relation of mutual similarity/interchangeability/indistinguishability with respect to certain properties, between objects. 
Formalizing this in mathematics; a binary relation $R$ on set $X$ is an equivalence on $X$ if it is reflexive, symmetric, and transitive.

It is possible to extend the relation into an equivalence containing the relation.
The order has to be respected. That is,
$$S = (R \cup R^{-1})^*$$ 
The equivalence class of element $a$ in equivalence $R$ we say that $$[a]_R := \{x \in X ~:~ xRa\}$$The set of all element which are equivalent to one another.
Then, we achieve some properties. 
- $a \in [a]_R$
- $b,c \in [a]_R \implies bRc \land cRb$
- $aRb \implies [a]_R=[b]_R$ 
- $\neg (aRb) \implies [a]_R \cap [b]_R = \emptyset$ 

A set partition... missing.

According to the properties of equivalence classes, every equivalence relation on set $X$ defines a partition of this set. Any partition of set $X$ defines an equivalence relation.

something, something... partial relation...

Final section, partial order relations.
Informally, it is a relation that allows comparing or sorting some elements of a set, meaning "element $a$ is before element $b$".
Such a comparison is not necessarily solution of a sorting problem you know from programming. It is not given that we can compare all the elements.
A partial order relation is a relation that is reflexive, antisymmetric, and transitive. The pair $(X,R)$ is called a partially ordered set or poset.
For denoting an order relation, the symbol $\preceq$ is used.

i give up

