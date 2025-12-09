[[LECTURE 18 - PART 2]]
# Cardinality of Sets

The cardinality is a way to be comparing two sets by their sizes.
If we have a finite set, then it is in-fact evaluated to a natural number.

The cardinality of an empty set $| \emptyset| \leq |A|, |\emptyset| \leq |\emptyset|, |\emptyset| = |\emptyset|$ 
Two sets have the same cardinality if there exists a bijective mapping between them. 

A set is defined as finite if there exists $m$ such that $|A| = |{1,2,...,m}|$
When it is not finite, an infinite set is called countable finite if $|A| = |N|$,
otherwise, it is called uncountable.
By Theorem, $N$ is the smallest infinite set.

If $A$ has more elements than $B$, the mapping cannot be injective.
If $B$ has more elements than $A$, the mapping cannot be surjective.
Essentially, if the sets have different amount of elements, there cannot be a bijection.
Therefore, the cardinalities are different.

Another theorem states...
If there is an injective mapping from $A$ to $B$, and another injective mapping from $B$ to $A$, then we know that there exists a bijective mapping between the two. Thus, $|A| = |B|$ 
If $|A| \leq |B|$ and $|B| \leq |A|$ then $|A| = |B|$
**Cantor-Bernstein-Schroeder** Theorem.

We can combine the two theorems, and find an injective mapping from our infinite set to the natural numbers, and then we may prove that their cardinalities are equal.

Let $A$ be a finite set. Then ever $B \subseteq A$ is finite too, and $|B| \leq |A|$ 
Additionally, the cardinality of the union of several sets is always less or equal to the sum of the cardinalities of all those sets (as the duplicates will be 'removed' in the union).
Then, according to inclusion exclusion principle$$\bigcup_{i=1}^n A_i = \sum_{k=1}^n (-1)^{k-1} \sum_{1\leq i_1 \leq i_2 \leq ... \leq n} |A_{i1} \cap ... A_{ik}|$$      
We can always shift the natural numbers to the right as there is no single greatest natural number. Therefore, we have injection $f: N_0 \rightarrow N$  $f(n) := n+1$ 
We may also find a injection $f: Z \rightarrow N$   $f(n) := (n \geq 1) 2n$ and $(n \leq 0) -2n+1$
It is also possible to find injection $f: N \times N \rightarrow N$ using the idea of an infinite amount of prime numbers and other ideas from number theory. $f(k,l) :=$ (k-th prime number)$^l$ 
Additionally, $f: Z \times Z \rightarrow N$ such that:
![[Pasted image 20251209145816.png]]
And clearly, $|Z \times N| \leq |Z \times Z|$

The mapping $f: Q \rightarrow Z \times N$ that assigns each $x \in Q$ the pair $p \in q$ such that $x=\frac{p}{q}$ and $p,q$ are coprime, is injective.
We can then compose it into a mapping from $f: Q \rightarrow N$

To tie this to cardinality, $|Q| \geq |Z \times N|$

The interval between 0 and 1 of real numbers is uncountable. The set of real numbers is uncountable. In fact, the cardinality of $(0,1)$ is the same as the entire set (uncountable).
Proof by contradiction using Cantor's Diagonal Lemma

About cardinality of infinite sets.
If B is infinite, if $|A| \leq |B|$ then $|A \cup B| = |B|$
Given they are also nonempty sets, and $|A| \leq |B|$, $|A \times B| = |B|$ 
If they both hold this requirement, then $|A \cup B| = |A \times B|$

They could ask you about the cantor theorem or to find a bijection to prove the cardinality is the same.

By cantor's theorem, $|A| < |P(A)|$ for every set $A$.

A set to the power of another set...
It's all of the different potential mappings from A to B.
It's every single possible mappings.

$|B^A| = |B|^{|A|}$ 
Let $A$ be a set. $|P(A)| = |{0,1}^A|$ 
In particular, when $A$ is a finite set, $|P(A)| = 2^{|A|}$

