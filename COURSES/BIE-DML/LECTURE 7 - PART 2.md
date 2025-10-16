[[COURSES/BIE-DML/LECTURE 8 (TUTORIAL)|LECTURE 8 (TUTORIAL)]]
# Mathematical Proofs, Mathematical Induction

We will be moving on from logic as it was the foundation to express and understand mathematics. It will still be used in this course and others, however these proofs are considered a different topic.
There is a misconception that mathematical proofs are only used to prove mathematical theorems. However, mathematical proofs are a tool to objectively show an undeniable truth - an act useful in many situations. It is useful in algorithms, where you need to verify that the algorithm works for every case. Or, even, given a complicated task to divide it into individual task, also requires some sort of mathematical proofs.

Before proofs, it is important to understand notation.
Integers: Z = {0, 1, -1, 2, -2, 3, ..}
Natural Numbers (positive integers): N = {1, 2, 3, ...}
Non-Negative Integers: $N_0$ = {0, 1, 2, 3, ...}.
To denote that a variable or constant belongs to a certain set, 
for example, x belongs to Integers, $x \in Z$ is used.

The notation for a sum of all numbers in a given range, for example, from a series:
$$\sum_{i=k}^{l} a_i = a_k+a_{k+1}+...+a_{l}$$
Likewise, for the product,
$$\prod_{i=k}^{l} a_i = a_k+a_{k+1}+...+a_{l}$$

An empty product is equal to one, an empty sum is equal to zero.
That may occur when the lower bound is greater than the higher bound

In logic, we are introduced to formulas and formal mathematical language. However, when discussing proofs, for convenience, we may use abbreviation and 'abuse' of the notation. 
For example, for quantifiers and predicates:
$(\forall x)(x \in Z \implies F)$ we simply write $(\forall x \in Z)F$
$(\exists x)(x > 0 \land F)$ we simply write $(\exists x > 0)F$

Going further, with simplification, we can merge the same type of restricted quantifiers.
Instead of $(\forall x > 0)(\forall y > 0)(x * y > 0)$
we simply write
$(\forall x, y > 0)(x * y > 0)$


In pure logic we distinguish between equivalence and logical equivalence, and likewise between implication and logical consequence. Outside pure logic, we will use equivalence and implication instead of equivalence and logical consequence, respectively. When we write $A \iff B$  we simply mean "$A \iff B$ is true"  . 
This only holds to outside pure logic.

Now with the setting ready, we may talk about proofs.

We will be discussing statements involving implication or equivalence, or properties of integer and objects from sets that can be indexed by integer numbers.
Notation of an end of a proof: Q.E.D.


When proving statements with quantifiers, it is important to look at a general variable. for $(\forall x \in A)F$ we take an arbitrary x from set A without further restrictions or specifications and prove F for this x.
$(\exists x \in A)F$ 
we find an x in the set A that satisfies F.



### Proof of Implication
**Direct proof** of an implication consists of a finite number of correct deductions, giving a chain of consequences through which we reach B. Thus, if there exists a finite sequence of formulas A, such that:
$(A \implies A_1) \land (A_1 \implies A_2) \land ... \land (A_n \implies B)$
then $A \implies B$

![[Pasted image 20251014154835.png]]

Of course, someone could ask you to explain why something even plus one is odd.
However, we need to rely on some common knowledge, axioms.
The professor recommends to only 'dig deep enough' to the point where you may be able to reasonably and logically explain it to a colleague.



**Indirect proof** of implication $A \implies B$ uses the contraposition law. In fact, it is a direct proof of implication $\neg B \implies \neg A$.

Without loss of generality (WLOG) will be needed in proofs, used in situations where we can divide the statement into several cases so that the proof of the statement for all the cases is the same or very similar. Then we will prove the statement for only one of the cases, and then the proofs for the remaining cases might be obvious or entirely fall in line.
![[Pasted image 20251014155539.png]]


**Proof by contradiction** of implication $A \implies B$ uses logical equivalence:
$$((A\land \neg B)\implies \bot) \equiv \neg(A\land \neg B) \lor \bot \equiv \neg(A\land \neg B) \equiv A \implies B$$
If we assume that a statement is not true, and following this lack of truth some nonsense follows, then we know for sure that it has to be true.
Thus, assume A holds and at the same time the negation of the consequence, $\neg B$ holds. If we can imply a **contradiction**, then the logical equivalence above ensures the original implication $A \implies B$ is true.

![[Pasted image 20251014155953.png]]