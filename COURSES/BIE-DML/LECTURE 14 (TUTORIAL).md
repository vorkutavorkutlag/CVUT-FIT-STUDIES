
[[COURSES/BIE-DML/LECTURE 15 (TUTORIAL)]]
# Sets and Mappings

Definition of set operations:
$A = \{n \in U : n \in A\}$ -> all elements of A
$A \cup B = \{n \in U: n \in A \lor n \in B\}$ -> all elements of A and B
$A \cap B = \{n \in U: n \in A \land n \in B\}$ -> all elements existing in both A and B
$\overline A$ = $\{n \in U: n \not \in A\}$ -> all elements that are not in A
A \ B = $\{n \in U: n \in A \land n \not \in B\}$ -> all elements of A that are not in B

$A = B \equiv \forall n \in U n \in A \iff n \in B$
$A \subset B \equiv \forall n \in U n \in A \implies n \in B$    

One way to have an intuition is to draw the venn diagram of a set. 

It is possible to convert set notations to propositional logic. For example, given sets X,Y,Z...
$a \in X \cap (Y \setminus Z) \equiv a \in X \land a \in (Y \setminus Z)$
$\equiv a \in X \land a \in Y \land a \not \in Z$ 
$a \in (X \cap Y) \setminus (X \cap Z) \equiv ... \equiv a \in X \land a \in Y \land a \not \in Z$ 
May be used to prove formally properties of set operations (such as distributivity here).

When wanting to disprove a formula, it is necessary to find a counterexample of the false proof. It is easiest to assume that the universe has the same amount of elements as the number of sets minus one. For example, for sets X,Y, Z, assume the universe consists only of $\{a, b\}$, and let $X=\{a\}$ $Z=\{b\}$ $Y=\{\emptyset\}$ . Then, plug the elements into the equations and demonstrate that they are not equal to one another.

When dealing with higher dimensional sets and universes, such as, for example, $R^2$, the logic persists. Though it is important to remember that we are then dealing not with a single element, but with a n-tuple. For example, for a cartesian product:
$(a, b) \in X \times (Y \cup Z) \equiv (a \in X) \land (b\ \in (Y \cup Z))$ 
The first element of the pair belong to the first object in the cartesian product. The second element belongs to the second object in the cartesian product. For n amounts of products, the nth element will belong to the nth set, connected by conjunctions.

Side note, the empty set $\emptyset$ is the only set that is a subset of any set in any universe.


Now, to mappings

A mapping is a machinery which receives as input an element of set A and transforms it into an element of set B. 
$f: A \rightarrow B$ 
A is the domain of the mapping. All possible inputs; $D(f)$
B is the codomain.
The actual set of all possible outputs is the image set; $Im(f) \subseteq B$ 

The mapping from every binary string to its length will be defined as:
$f:\{0,1\}^* \rightarrow N_0$ 
The star above the set denotes every possible string made of those elements
The mapping from every pair of real numbers to the bigger one of the two will be defined:
$f: R^2 \rightarrow R$ 
As the first set is the cartesian product of $R \times R$.

Not all mappings were boring the same.
It may happen when two elements from A are assigned the same element in B in a mapping.
When for every mapping from A to B, the result is different, it is called **injective mapping**.
$\forall a,b \in A a \neq b \implies f(a) \neq f(b)$ or likewise
$\forall a, b \in A f(a) = f(b) \implies a = b$

When the image set of f corresponds to the codomain of f, 
If for every b in B, there exists an a in A such that f(a) = b, it is **surjective**.
$\forall b \in B \exists a \in A f(a) = b$

If a function is both injective and surjective it is called a **bijective** function.

For example, the mapping: $f: Z \rightarrow Z$ such that $n \rightarrow n+1$ 
If $f(a) = f(b)$ then $a+1 = b+1$ therefore $a=b$ and it is injective.
For every $b \in B$, there exists an $a \in A$ such that $f(a) = b$.
$f(a) = b \implies a + 1 = b \implies a = b - 1$ therefore it is surjective.
Thus, being both injective and surjective, it is a bijection.

However, if the domain and codomain were instead $N_0$ we would find that there exists an element in $N_0$ such that for all a in $N_0$ , $f(a) \neq 0$ 
$\exists 0 \in N_0$ s.t. $\forall a \in N_0 f(a) \neq 0$ 
That is because the only number whose successor is 0 is negative one, which is not in our domain.

