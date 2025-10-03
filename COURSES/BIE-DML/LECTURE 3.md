[[LECTURE 4 (TUTORIAL)]]
### Propositional Logic (Continued)

It is important to note that in human, informal language, multiple different phrasings can mean the same logical expression.
If it is a Cow (C) then it eats grass (G):$$C \implies G$$
It can be rephrased in the English language in various formats:
- When an animal is a cow, then it eats grass.
- An animal is a cow only if it eats grass.
- The animal isn't a cow or it eats grass.
- It eats grass if it is a cow.
Contrapositive
- If it does not eat grass it is not a cow $$\neg G \implies C$$
Negation:
- It is a cow, but it does not eat grass

Although, in some cases, the same can apply for formal logic as well.
John can speak French (J). Peter can speak French (P).
Neither John nor Peter can speak French:
$$\neg J \land \neg P$$
Can also be expressed as:
$$\neg (J \lor P)$$
$$=> (\neg J \land \neg P) \equiv \neg (J \lor P)$$




#### Implication
==========

The following formulas are logically equivalent:
$$A \implies B$$
$$\neg A \lor B$$
$$\neg B \implies \neg A$$
$$\neg (A \land \neg B)$$
#### Equivalence
==========
The following formulas are logically equivalent:
$$A \leftrightarrow B$$
$$(A \implies B) \land (B \implies A)$$
$$(\neg A \lor B)\land(\neg B \lor A)$$
$$(A \land B) \lor (\neg A \land \neg B)$$
$$\neg A \leftrightarrow \neg B$$

### Complete Systems of Connectives
================================

It is not necessary to have all of the connectives. Every single formula can be expressed as negation, junction and disjunction. Moreover, it is possible to express all propositional fo rmulas using each of these sets individually:
$$\{\neg, \lor\}$$
$$\{\neg, \land \}$$
$$\{\neg, \implies\}$$

We will prove that {¬, ∨} is a functionally complete system. For the other
systems see tutorial handouts.

$$A \implies B \equiv \neg A \lor B$$
$$A \leftrightarrow B \equiv (A \land B) \lor (\neg A \land \neg B) \equiv \neg (\neg A \lor \neg B) \lor \neg(\neg \neg A \lor \neg \neg B) \equiv $$
$$\neg (\neg A \lor \neg B) \lor \neg (A \lor B)$$

##### Sheffer Symbol and Piece Arrow
We define the Sheffer symbol (or NAND)
$$A\uparrow B \equiv \neg (A \land B)$$
We define Pierce arrow (or NOR)
$$A \downarrow B \equiv \neg(A \lor B)$$

If done properly, it would use induction on the structure of propositional formulas. informally, we will show that each logical connective can be replaced by NAND.
$$\neg A \equiv \neg (A \land B) \equiv A \uparrow A$$
...
![[Pasted image 20250930145958.png]]

In DML, NAND and NOR will not be used. This is simply an example of the fact you can abbreviate and swap out logical expressions for one another.

### Logical Consequence

The equivalence is defined by both expressions on both sides having the same logical expression and truth tables.
Logical consequence is a one-sided equivalence, as in, from A, follows B. A entails B. A logically implies B.
If for each truth valuation v such that v(A) = 1 we have v(B) =1, we write:
$$A \vdash B$$
As opposed to implication, which is a propositional formula, a logical consequence is a relation of propositional formulas. It is a different object in a sense, a relation in a meta-language. An implication gives you another formula, whereas the logical implication is a binary relation - It is not another formula.
Logical consequence is a statement, implication is a formula.

Basic logical consequences:
$$A \land B \vdash A$$
$$A \vdash A \land B$$
$$\neg A \vdash A \implies B, B \vdash A \implies B$$
$$A \vdash T, \bot \vdash A$$

For any formulas E,F and G of propositional logic, we have that:
1.
$$E \vdash E$$

2.
if $$E \vdash F$$
and $$F \vdash G$$
then $$E \vdash G$$

3.
if
$$F \vdash G$$
then
$$E \land F \vdash E \land G$$

4.
Same as 3, but disjunction replaces the junction.

5.
$$E \equiv F$$
if and only if
$$E \vdash F \land F \vdash E$$



In order for a logical implication to occur, both sides should be true. i.e.:
$$(C \implies G) \land G \vdash C$$
Is not true, because the definition is anytime that the formula on the left is true, teh right must also be true. In this case, only if both conjuncts are true the formula is true. So, G must be true. C => G can be true for every value of C, and this lack of limitation for C's values means that that the implication is NOT TRUE.
However:
$$(G \implies C) \land G \vdash C$$
Both conjuncts have to be true for this matter. So, G is true, and the implication of every truth is necessarily a truth. And so, C has to be true also. Meaning, both sides of the statements are true, Q.E.D the logical implication is TRUE.

###### Theorem
======
A entails B if and only if A implies B is a tautology.
A implies B if and only if A and neg B is a contradiction.

![[Pasted image 20250930152525.png]]A counterexample is an example that contradicts a theory.
For example, "Every prime number is odd." has a counterexample being that of 2 being a prime number and being even.

##### Disjunctive Normal Form (DNF)
======================
Literal is an elementary formula or its negation.
Implicant is a literal of conjunction of literals.
Formula is in a disjunctive normal form if it is an implicant or a disjunction of implicants.
For example:
Literals: A; neg A; B; neg B;
Implicants: A land neg B; neg A land C land B; neg C;
DNF: (A land B land C) lor (neg A land neg C)
		(A ∧ B ∧ C ) ∨ (¬A ∧ ¬C )

DNF: (A ∧ ¬B) ∨ (¬A ∧ C ∧ B) ∨ ¬C 
DNF: A; ¬A; A ∨ B; A ∧ ¬B 


Every literal is an implicant, and every implicant is already DNF and CNF.

##### Conjunctive Normal Form (CNF)
=======================
Literal is an elementary formula or its negation.
Clause is a literal or a disjunction of literals.
Formula is in a conjunctive normal form (CNF) if it is a clause or a
conjunction of clauses.
For example:
Clauses: A ∨ ¬B; ¬A ∨ C ∨ B; ¬C
CNF: (A ∨ ¬B) ∧ C
CNF: (A ∨ ¬B) ∧ (¬A ∨ C ) ∧ ¬C 
CNF & DNF:  A; ¬A; A ∧ ¬B; A ∨ ¬B (!!!) 


CNF: Conjunctions outsides, disjunctions inside.
DNF: Disjunctions outside, disjunctions inside.
To swap between CNF and DNF and vice versa it is possible to use distributive laws in both directions. Occasionally, we use universal bound laws and omit contradictions in DNF and tautologies in CNF. We used absorption laws to simplify.
![[Pasted image 20250930153748.png]]


For every formula there is a logically equivalent formula which is in DNF
and a logically equivalent formula which is in CNF. When we negate a DNF of a formula we get a CNF. However, this CNF is a negation of the original formula (i.e. not a CNF of the original formula!), and vice versa
DNF and CNF are not unique (e.g. (¬A ∨ B) ∧ B and B are both CNF of
the same formula).

##### Full DNF/CNF
==========
Minterm is an implicant (DNF) which contains all elementary formulas.
Maxterm is a clause (CNF) which contains all elementary formulas.
Formula is in full DNF if it is a disjunction of (distinct) minterms.
Formula is in full CNF if it is a conjunction of (distinct) maxterms.
![[Pasted image 20250930154000.png]]


For every formula there is a logically equivalent formula which is in full
DNF and a logically equivalent formula which is in full CNF, and they are unique.
![[Pasted image 20250930154103.png]]

DNF is true for each one of its minterms is true.
CNF is true only for all its maxterms is true.

![[Pasted image 20250930155330.png]]

CNF is used to easily find what truth valuations make the formulas false.
You can easily find it as it will all be true but one valuation. You may negate it and turn it into a minterm, and analyze it that way and get a symmetrical result.

![[Pasted image 20250930160048.png]]