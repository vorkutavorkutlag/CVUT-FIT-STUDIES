[[COURSES/BIE-DML/LECTURE 13 (TUTORIAL)]]
# Sets, Continued

Visualizing sets has various methods, including Venn Diagrams, denoting the universe in which we are working with, and within circles depicting sets. It is not rigorous enough to visualize more complex situations.

#### Power Set
If A is in the universe, then we define the power set of A to be the set of all subsets of A, denoted P(A), i.e. $P(A) = {X \subseteq U : X \subseteq A}$ 
As a warning, P(A) is a subset of different universe than A, its elements are sets containing elements of A.

##### Proposition
Propositional logic can still be used to prove statements about sets. By the definition of set properties, such as set inclusion, we may derive formulas and use logical laws, such as logical consequence, to reach our proof.

#### Set Operations
Consider $A, B \subseteq U$ We define

**complement** of set A: $\overline A$ := $\{x \in U : x \notin A\}$ 
all universe elements which are not in A

**intersection** of sets A and B: $A \cap B := \{x \in U : x \in A \land x \in B\}$ 
all elements that belong to both A and B

**union** of sets A and B: $A \cup B := \{x \in U: x \in A \lor x \in B\}$
all elements that belong either to A or B

**difference** of sets A and B: $A$ \ $B$  := $\{x \in U: x\in A \land x \notin B\}$ 
all elements in A that are not in B

**Cartesian product** of sets A and B:
$$A \times B := \{(a, b) \in U \times U : a \in A \land b \in B\}$$
A set in a new universe of ordered tuple.

##### & logical connectives
The statement "x belongs to set M" where M is obtained by applying some set operations to sets A, B, C, etc. is equivalent to a formua which is obtained by an analogous application of the corresponding logical connectives to atomic formulas. This is because the following equivalences are true.
$$x \in \overline A \iff \neg(x \in A)$$
$$x \in (A \cap B) \iff ((x \in A) \land (x \in B))$$
$$x \in (A \cup B) \iff ((x \in A) \lor (x \in B))$$
$$(x \in \emptyset) \iff \bot$$
$$(x \in U) \iff \top$$

##### Fundamental Laws
**Law of Complement**: $A \cup \overline A = U$ , $A \cap \overline A = \emptyset$ 
**Involution Law**: $\overline{\overline A} = A$
**Laws of Unity**: $A \cup \emptyset = A$ , $A \cap U = A$  
**Laws of Zero**: $A \cup U = U$, $A \cap \emptyset = \emptyset$ 

##### Algebraic properties
**Commutative Laws**
$A \cup B = B \cup A$ 
$A \cap B = B \cap A$
**Associative Laws**
$A \cup ( B \cup C) = (A \cup B) \cup C)$ 
$A \cap (B \cap C) = (A \cap B) \cap C$ 
**Distributive Laws**
$A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$  
$A \cup ( B \cap C) = (A \cup B) \cap (A \cup C)$ 
**Laws of Indempotence**
$A \cup A = A$
$A \cap A = A$
**Laws of Absorption**
$A \cup (A \cap B) = A$
$A \cap ( A \cup B) = A$
**De-Morgan's Laws**
$A$ \ $(B \cup C) = (A$ \ $B) \cap (A$ \ $C)$
$A$ \ $(B \cap C) = (A$ \ $B) \cup (A$ \ $C)$
Special case for $A = U$:
$\overline{(B \cup C)} = \overline B \cap \overline C$
$\overline{(B \cap C)} = \overline B \cup \overline C$


Following are generalized operations to define large amounts of elements:
![[Pasted image 20251104161500.png]]

Two sets are disjoint if their intersection is an empty set.

### Mapping
Typically when talking about mapping, you would think of real functions with real variables or about sequences which are mappings from integers to real numbers. These are all examples of mappings we've met in the past. Typically we imagine mappings as an assignment of elements from one set to another.
##### Definition
Let $A, B$ arbitrary nonempty sets. A mapping $f$ from $A$ into $B$ is any set $f \subseteq (A \times B)$ such that for every $a \in A$ there is at most one $b \in B$ satisfying $(a, b) \in f$
It is a subset of a Cartesian product that satisfies that for every element A there is at most one element in B. What must not happen is that above one A element there would be more than one B element. 
It could be thought as a real function with real variables. We are identifying the mapping with its graph, where axis-x is the A set and axis-y is the B set. 

The **domain** of a mapping $f$ as the set $D(f) := {a \in A: (\exists b \in B)(f(a) = b)} \subseteq A$ 
the **range** (or **image set**) of a mapping $f$ as the set $Im(f) := {b \in B: (\exists a \in A)(f(a) = b)} \subseteq B$ 

The subset notation in the end is just for emphasis that it is a subset, and is redundant for the actual definition of the domain and range.
We say that a mapping $f: A \rightarrow B$ is **total** if $D(f) = A$ . That is, $f \subseteq (A \times B)$ is a total mapping if and only if for every $a \in A$ there is **exactly one** $b \in B$ satisfying $(a, b) \in f$.

There's plenty of information I haven't written here. Refer to the lecture slides.