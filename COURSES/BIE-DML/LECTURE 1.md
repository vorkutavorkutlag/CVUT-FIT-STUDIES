# CLASSICAL LOGIC

### The law of non-contradiction
- not (F and not F)
- "Nothing can be and not be."
### The law of excluded middle
- F or not F
- "Everything must either be or not be." - logic is binary, there is no third possibility

### The law of identity
- F= F
- "Whatever is, is." Mathematical objects do not change over time.

#### Definition
An elementary proposition is a simple indicative sentence for which it makes sense to ask whether it is true or false. Elementary propositions are denoted by capital letters, e.g. A, B, C, A_1, A_2.... We call them elementary formulas.


![[Pasted image 20250923145829.png]]

### Language of Propositional Logic

Logical connectives: ¬, ∧, ∨, ⇒, ⇔
Formulas are denoted by capital letters: A, B, C, etc.
Restrained within parentheses ()
If E , F are formulas, then so are
$$¬E , (E ∧ F ), (E ∨ F ), (E ⇒ F ), (E ⇔ F ).$$
Instead of using correct syntax, e.g.
$$(A ∧ B), ((¬A) ⇒ B) , ((A ⇒ B) ∨ (¬((A ∧ B) ∨ B)))$$
we simply write
$$A ∧ B, ¬A ⇒ B, (A ⇒ B) ∨ ¬((A ∧ B) ∨ B)$$

Subformula: Any part (sequence of symbols from the language of propositional logic) of a formula which is a formula in itself is called a subformula
A formula is satisfiable if there exists a truth valuation v with v(F) = 1, and is unsatisfiable otherwise. 
If F is true for every valuation, it is a tautology (always true). If F is false for every valuation, it is a contradiction (always false). A tautology is a negation of a contradiction, and the other way around. Tautology is satisfiable, whereas Contradiction is unsatisfiable/

#### Logical equivalence
Formulas E, F are logically equivalent (E ⊨ F) if v(e) = v(F) for every valuation v.
E ⊨ F if and only if E ⇔ F is a tautology.
Properties of ⊨|:
- E⊨E
- if E⊨F then F⊨E
- if E⊨F and F⊨|G, then also E⊨G 

![[Pasted image 20250923152051.png]]

## Logical Laws

- A ∨ ¬A  : logic is binary
- ¬(A ∧ ¬A) : contradiction
- ¬¬A ⇔ A : we can drop double negation

⊤ denotes a tautology. ⊥ denotes a contradiction.
A ⊨ T means A is a tautology
A ⊨ ⊥ means A is a contradiction.

- A ∧ ⊤ ⊨ A: identity law 
- A ∨ ⊥ ⊨ A: identity law
- A ∧ ⊥ ⊨ ⊥: universal bound
- A ∨ ⊤ ⊨ ⊤: universal bound

Let A and B be formulas of propositional logic. Then
1. A ∧ A ⊨ A . . . idempotent law for ∧
2. A ∨ A ⊨ A . . . idempotent law for ∨
3. A ∧ B ⊨ B ∧ A . . . commutative law for ∧
4. A ∨ B ⊨ B ∨ A . . . commutative law for ∨
5. (A ∧ B) ∧ C ⊨ A ∧ (B ∧ C ) . . . associative law for ∧
6. (A ∨ B) ∨ C ⊨ A ∨ (B ∨ C ) . . . associative law for ∨
7. (A ∧ B) ∨ C ⊨ (A ∨ C ) ∧ (B ∨ C ) . . . distributive law
8. (A ∨ B) ∧ C ⊨ (A ∧ C ) ∨ (B ∧ C ) . . . distributive law
9. A ∧ (A ∨ B) ⊨ A . . . absorption law
10. A ∨ (A ∧ B) ⊨ A . . . absorption law

##### Distributive Laws
$$(A ∧ B) ∨ (C ∧ D) ⊨ (A ∨ (C ∧ D)) ∧ (B ∨ (C ∧ D)) ⊨
 (A ∨ C ) ∧ (A ∨ D) ∧ (B ∨ C ) ∧ (B ∨ D)$$
 In general:
 $$(A_1 ∧ . . . ∧ A_n) ∨ (B_1 ∧ . . .∧ B_m) ⊨ (A_1 ∨ B_1) ∧ (A_1 ∨ B_2) ∧ . . . ∧ (A_n ∨ B_m)$$
Analogously:
$$(A ∨ B) ∧ (C ∨ D) ⊨ (A ∧ (C ∨ D)) ∨ (B ∧ (C ∨ D)) ⊨
⊨ (A ∧ C ) ∨ (A ∧ D) ∨ (B ∧ C ) ∨ (B ∧ D)$$
In general:
$$(A_1 ∨ . . . ∨ A_n) ∧ (B_1 ∨ . . . B_m) ⊨⊨ (A_1 ∧ B_1) ∨ (A_1 ∧ B_2) ∨ . . . ∨ (A_n ∧ B_m)$$

#### Theorems

De Morgan Law:
$$¬(A ∧ B) ⊨ ¬A ∨ ¬B $$
- additionally
$$¬(A ∨ B) ⊨ ¬A ∧ ¬B $$

Negation of implication:
$$¬(A ⇒ B) ⊨ A ∧ ¬B $$
Negation of equivalence:
$$¬(A ⇔ B) ⊨ ¬A ⇔ B ⊨ A ⇔ ¬B $$


Sidenote:
All the following are the same logically.
1. A ⇒ B
2. ¬A ∨ B
3. ¬B ⇒ ¬A
4. ¬(A ∧ ¬B)
