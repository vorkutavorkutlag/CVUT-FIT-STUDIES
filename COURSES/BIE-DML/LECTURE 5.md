[[LECTURE 5 - PART 2]]
### Completing Propositional Logic
===============================

Full CNF$$A \iff B \equiv (\neg A \land \neg B) \lor (A \lor B)$$
Full DNF
$$A \iff B \equiv ()$$
The minterm relates to the truth valuation which makes the formula true.
The maxterm relates to the truth valuation which makes the formula false.

Logical implication
$$A \vDash B$$
B is true whenever A is true, A is false whenever B is false.
if B is true, A is not necessarily true. if A is false, then B is not necessarily false.

$$A \land B \vDash A \vDash A \lor B$$
If, given a full DNF, 
$E \equiv (A \land B \land \neg C)$, and 
$F \equiv (\neg A \land B \land \neg C) \lor (\neg A \land \neg B \land \neg C) \lor (A \land B \land \neg C)$
We see that if E is true, then F is necessarily true as well. 
However, if F is true, it does not necessarily mean E is true.
This means logical consequence exists such that: $E \vDash F$

A summary of all logically equivalent formulas.
![[Pasted image 20251007145618.png]]

## Summary of Propositional Logic
=================================

We defined a formula, we define a truth valuation, different types of formulas (satisfiable, contradiction, tautology), necessary & sufficient, logical laws and equivalence, functionally complete systems, logical consequence, DNF, CNF.
You will be expected to know logical laws by heart. Cheat sheets will not be allowed.