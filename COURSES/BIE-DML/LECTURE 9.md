[[LECTURE 9 - PART 2]]

As a followup on mathematical proofs.

### Proof by Cases
Any formula E can be viewed as an implication. i.e. $E \equiv T \implies E$
Applied in the case that A implies a disjunction of several alternative.s If B follows from each of them, then the implication of $A \implies B$ holds. i.e., a proof with three alternatives is:

$((A \implies (D \lor E \lor F)) \land (D \implies B) \land (E \implies B) \land (F \implies B)) \vDash (A \implies B)$

For example, we will be able to prove $(n^3-n)$ is divisible by 3, we may split it into:
$n = 3k$
$n = 3k + 1$
$n = 3k + 2$

Then we insert these cases into the formula and show that in every case it is divisible by 3.

### Proof by Equivalence
Equivalence $A \iff B$ can be proven e.g. in the following ways:
direct proof, that is proving
$(A \iff A_1) \land (A_1 \iff A_2) \land ... \land (A_n \iff B)$
as a proof of two implications
$(A \implies B) \land (B \implies A)$
$(A \implies B) \land (\neg A \implies \neg B)$

### Chain of equivalences

When proving theorems like "Statements, A, B, C D are equivalent"
It is not necessary to prove the equivalence of every pair. A better approach is to create a chain (circle) of implications, e.g.
$(A \implies B) \land (B \implies C) \land (C \implies D) \land (D \implies A)$
or a star of equivalences
$(A \iff B) \land (A \iff C) \land (A \iff D)$


## Weak Mathematical Induction

Consider a set that is created by successively adding elements - the first few are explicitly listed and then there are rules for creating new elements from already existing ones. Next, consider some property P that we want to prove for all elements of the set. We can prove it by induction if we do two steps:
1. We prove that all the first explicitly listed elements satisfy property P.
2. For each element created using the rules, we prove that if the elements which it was created has property P, then it itself also has property P.

For example, in an informal example, if you start a rabbit farm and buy six brown rabbits, when they breed, you will still only have the same breed of rabbit (say, brown).
The property has to be reserved for all elements of a set out of which it was generated.

For example, the proof that ${\neg, \lor}$ is a functionally complete set in propositional logic is based on induction. It shows that all elementary formulas can be rewritten with these connectives. Every other formula is made from elementary formulas. Therefore, any formula can be written by this set.

#### Weak Principle
Let $n_0 \in Z$ and let $P(n)$ be a predicated on property of integers being true or false for ever $n \geq n_0$ Assume that the following conditions hold.
1. (Basis step) $P(n_0)$ is true
2. (Inductive step) The following implication holds for every $n \in Z, n \geq n_0$: "If $P(n)$ is true, then $P(n+1$) is true as well."
Conclusion: Then by the **weak principle of mathematical induction** $P(n)$ holds for every defined n.
The statement "$P(n)$ is true" in the inductive step is called the **inductive hypothesis**.
Symbolically written, it is the tautology:
$(P(n_0)) \land (\forall n \geq n_0)(P(n) \implies P(n+1))) \implies (\forall n \geq n_0)P(n)$

We have a chessboard with $2^n x 2^n$ squares,where $n \in N$ and one of its squares is crossed out. We claim that all remaining squares can be tiled without overlapping using L-shaped tiles covering 3 squares each. /-

The predicate P(n), that we want to prove to be true for every $n \in N$ is "Tiling with specific properties is possible for any board of the side length 2" with one square crossed out.

We establish:
$n_0 = 1$
Basis Step (BS): For n=1 we have a board with a side length $2^1 = 2$ and one crossed out square - the remaining squares form exactly one L shaped tile, so P(1) is true.

Inductive Step (IS): Let $n \geq 1$ and assume that we are able to tile any board with side length $2^n$ with any one of its squares crossed out, i.e. that P(n) is true. We will show that then we can also tile the board with side length $2^{n+1}$ having one square crossed out.

We tile three boards with side length $2^n$ leaving the green figure empty and then we tile the last board leaving the orange square empty.
![[Pasted image 20251021165430.png]]

Note that in mathematical induction, we do not prove P(n) itself, but only P(n_0) and then for every other n, the implication $P(n) \implies P(n+1)$ Both steps of the proof are equally important.

In the chain of equivalences, it is about the transitivity of equivalences, and in here, by using implication, we prove the relation of any two neighbors. Also, in the chains, it is defined for finite terms, whereas mathematical induction is defined for infinite, general terms.

It is important to remember that the statement we prove in the inductive step is:
$(\forall n \geq n_0)(P(n) \implies P(n+1))$ and NOT ($(\forall n \geq n_0)P(n)) \implies P(n+1)$
The quantifier applies for all predicates!

Sometimes, when we try to apply this principle, we will come across the problem that the hypothesis in the inductive step is not strong enough, or that the implication in the inductive step doesn't hold from $n_0$ but only holds from some integer ($n_m$), In this case:

## Strong Mathematical Induction


Basis Step: Proof that $P(n_m)$ holds.
Inductive Step: Consider n+1
If n+1 is defined by some other variables and terms that we cannot directly prove...
Let $n_0 \in Z$ and let $P(n)$ be a predicate that is either true or false for every $n \geq n_0$. Let $m \in N_0$ assume that the following conditions hold:
BS: $P(n_0), P(n_0 + 1), ..., P(n_0 + m)$
IS: The following implication is true for every $n \in Z, n \geq n_0 + m$

"If P(k) is true for every $k \in \{n_0, n_0+1,...,n\}$  then $P(n+1)$ is true as well."

Conclusion: Then by the **strong principle of mathematical induction**, $P(n)$ holds for every $n \in Z, n \geq n_0$.
The statement "If P(k) is true for every $k \in \{n_0, n_0+1,...,n\}$" in the implication of the induction is called the **inductive hypothesis**.
Symbolically, it is the tautology:
$((\forall k \in \{n_0, ..., n_0+m\})P(k) \land (\forall n \geq n_0 + m((\forall l \in \{n_0,..., n\})P(l) \implies P(n+1)))$
$\implies$
$(\forall n \geq n_0)P(n)$

$m$ - for how many cases in the beginning we prove the property.
Usually, you want to start with the inductive step, and afterwards it becomes more clear what $m$ should be.



Inductive (recursive) approach can be used to define e.g.
* functions (mappings)
* sets
* data structures and other interesting objects.
The union of n+1 sets is the union of the first n sets and the union of that with n+1st set.