[[COURSES/BIE-DML/LECTURE 5|LECTURE 5]]
Test on October 20th at the beginning of the tutorial.
Quizzes on MARAST are open now.

#### Formulas
========

Statements can be expressed and formalized with formulas.
$$A \implies B \equiv \neg A \lor B$$
$$\neg (A \implies B) \equiv A \land \neg B$$
This can be proven by their truth tables being exactly the same.

If A is necessary for B, then:
$$B \implies A$$
Upon the existence of B, A must exist.
If A is sufficient of B, then:
$$A \implies B$$
The existence of A alone means B can exist.
If A is sufficient and necessary for B:
$$A \leftrightarrow B$$

###### Golden rule
========
$$A \implies B \equiv (\neg A \lor B)$$
$$\neg (A \implies B) \equiv \neg (\neg A \lor B) \equiv \neg \neg A \land \neg B \equiv A \land \neg B$$
![[Pasted image 20251001181748.png]]
![[Pasted image 20251001181759.png]]
![[Pasted image 20251001183258.png]]


Some exercise using these laws have taken place, for example:
$$(A \land B) \implies (A \lor C)$$
Using the golden law to get rid of the implication, we get
$$(A \lor \neg A) \lor (...) \equiv T$$
Meaning it is a tautology, meaning this is a rule.
Simple formulas such as this can also be understood with intuition. The truth table always lines up correctly. If left is true, then A has to be true, then right will be true. If the left is false, then A is either true or false, meaning right will be true or false. That checks out for the implication truth table.

![[Pasted image 20251001185207.png]]

Distributive laws will be most important when discussing DNF and CNF. and can be used to separate values and 'spread' them out, as well as converting conjunctions and disjunctions (De Morgan is better for that exact need, though.)

Distributivity can be done with as many terms as needed. i.e.:
$$(A \lor B \lor C) \land D \equiv (A \land D) \lor (B \land D) \lor (C \land D)$$
Negation of equivalence:
$$\neg (A \leftrightarrow B) \equiv A \leftrightarrow \neg B \equiv \neg A \leftrightarrow B$$
This makes sense because logic is binary. 
If it is not 1, it necessarily has to be 0, and vice versa.


### Definitions of symbols for complete systems
==========================================
We can define NOR as a pierce/down arrow to express neither A nor B.
$$A \downarrow B \equiv \neg ( A \lor B)$$
For every of the following it is possible to express with NOR.
$$A \equiv A$$
$$\neg A \equiv \neg (A \lor A) \equiv A \downarrow A$$
$$A \lor B \equiv \neg \neg (A \lor B) \equiv \neg ( \neg (A \lor B)) \equiv \neg (A \downarrow B) \equiv (A \downarrow B ) \downarrow (A \downarrow B)$$
$$A \land B \equiv \neg (\neg A \lor \neg B) \equiv \neg A \downarrow \neg B \equiv (A \downarrow A) \downarrow (B \downarrow B)$$
$$A \implies B \equiv \neg A \lor B \equiv (\neg A \downarrow B) \downarrow (\neg A \downarrow B) \equiv ((A \downarrow A) \downarrow B) \downarrow ((A \downarrow A) \downarrow B))$$

Equivalence can be expressed as well, as we can express conjunction and implication both ways around.
Additionally, using truth tables, we can manually prove the lack of disassociativity by finding at least one false valuation. 