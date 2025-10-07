# Introduction to Predicate Logic
========================================

Upgrade of propositional logic which allows sophisticated arguments, with the use of objects (constants, variables, functions) their quantification (there exists, for all) and their mutual relationship/properties (predicates).
"Every natural number n is either even or odd"
"For every pair of real numbers, x, y, the sum of x + y is strictly less than the product x \* y"
"If everybody likes somebody, then also Charles likes somebody."
These sentences would be abstracted and turned into general ideas in propositional logic. However, in predicate logic, we give it more variable specific. For example.

Let r(x, y) denote the property that "x likes y", x, y represent people.
"If everybody likes somebody, then also Charles likes somebody."
Let C denote Charles.
$$(\forall x) (\exists y) r(x,y) \implies (\exists y) r (C, y)$$
For every x, there exists a y that satisfies r.
This implies that for some y, r is satisfied by r(C, ...).
Meaning, this is proof Charles likes somebody.

"Every natural number n is either even or odd"
$$(\forall n) (\exists m)(n=m+m) \lor (\exists k) (n = (k+k)+1)$$
For every natural number, there exists:
Either an m such that `n = m+m`
`OR`
Either a k such that `n = k + k + 1`


### Constants, Predicates and Functions
======================================

***Constants*** denote objects with specific meanings that do not change, e.g. numbers (0, 1, $\pi$, names, etc).

***Predicates*** are properties of objects/relationships among objects, e.g.:
p(x) - "x is from Prague", "x is a prime number".
r(x, y) - "x likes y", "x $\leq$ y", "x = y"
t(a, b, c) - "line segments of length a, b, c can make up a triangle".

The predicate is either true or false, that is the elementary, smallest formula. It is the smallest bit in predicate logic that can be either true or false.

***Functions*** are used for the formalization of mathematics, operations which assign a new object to one or more objects, e.g.:
f(x) = -x, $\sqrt x$ , sin(x), etc.
f(x, y) = x + y, x \* y, etc.
We always specify which constants, predicates and functions we will work with (a language)

***Quantifiers*** are operators for the quantity or amount of something.
Universal quantifier - "All" $\forall$; (for) every/any/all
Existential quantifier - "Exists" $\exists$; there exist(s)/there is/ there are/ **some**
We can view $\forall$ and $\exists$ as a generalized conjunction, resp. disjunction.
Not every variable which is in a formula needs to be quantified.
For example,
$(\forall n)(n \geq 0)$ means $1 \geq 0 \land 2 \geq 0 \land 3 \geq 0 \land etc...$


These are "infinite" statements that cannot be expressed in a finite form with propositional 
logic.

###### **By definition**
==========
The language of predicate logic consists of: logical symbols and
non-logical symbols. symbols for: logical connectives, variables, quantifiers, auxiliary (parentheses), symbols for constants (CAPITAL), symbols for predicates (lower), symbol for functions (lower).

A term is a string of symbols is a term if it can be obtained by a finite number of
the following steps: 
- Any variable or constant is a term
- if $t_1, ..., t_n$ are terms and f is function of arity (number of args) n then $f(t_1,...,t_n)$ is term.

A formula is a sequence of symbols from the language of predicate logic if it can be obtained by a finite number of the following steps.
If p is a predicate symbol of arity n, and $t_1,..., t_n$ are terms then $p(t_1,..., t_n)$ is a formula. We call it an ***atomic formula***.
if A, B are formulas then the negation and connectives of the two formulas are formulas.
If x is a variable and A a formula then ($\forall$x )A and ($\exists$x )A are formulas.

Any continuous sequence of symbols contained in a formula which is a
formula in itself is called a subformula.

![[Pasted image 20251007151857.png]]
![[Pasted image 20251007151907.png]]
The reason we don't have the formula $r(x, y) \implies r(C, y)$ is because it does not exist independently from the quantifiers of x and y. We would have to rewrite the formula and change its meaning entirely to isolate it and then we could define it as a subformula.
It depends on where the quantifier is.

Taking the previous formula,
$$(\forall x)(\exists y)r(x,y) \implies (\exists y)r(C,y)$$
`y` does not necessarily represent the same object on RHS and LHS
Additionally, we could equally well write:
$$(\forall x)(\exists y)r(x,y) \implies (\exists z)r(C,z)$$
Most of the time we will not use different variable names, and so we will be reusing them. It is important to note which ones are the same ones. These variables are called **bound** variables if they appear in some sort of quantifier. If they appear without a quantifier they are called **free**.
E.g. x is free and y,z, are bound in:
$$(\exists y) r(x, y) \implies (\exists z) r(C,z)$$
If a formula lacks any bound variables, it is an **open formula**.
If a formula lacks any free variables, it is a **closed formula**.

If a bound of a variable is not present, and it is free, it is ((allegedly)) equivalent to $\forall$





###### Natural language examples
Jane is from Prague but David is not
$$p(J) \land \neg p(D)$$
Somebody is from Prague
$$(\exists x) p(x)$$
Everybody is from Prague
$$(\forall x)p(x)$$
Nobody is from Prague
$$(\forall x) \neg p(x)$$
Nobody knows Nobody
$$(\forall x)(\forall y) \neg k(x, y)$$



When a variable is free, the formula's valuation is undefined and is dependent on n. When it is not yet defined, it is **open**. 
In the set N together with + and =, consider this formula:
$(\exists m)(n=m+m)$
However, when we bring bounds to variables, we make a **close** formula.
$(\exists n)(\exists m)(n=m+m)$ - true
$(\forall n)(\exists m)(n=m+m)$ - false
Note that is the domain was R, then both formulas would be true.

Example with set theory:
![[Pasted image 20251007154852.png]]

It is very tricky to define the truth in predicate logic. It uses the notion of Tarsky's definition of truth (not to be done in BIE-DML) We will still use the logical equivalence and consequence of two formulas but very vaguely. 
Roughly, we can say that a formula of predicate logic in a specific interpretation (specific domain and specific valuation of functions, predicates, variables and constants) is a formula of propositional logic. In that context, we can tell whether the formula is true or false.
$A \equiv B$ iff A and B have the same truth value for all interpretations
$A \vDash B$ iff in every interpretation, whenever A is true, also B is true
![[Pasted image 20251007155219.png]]
![[Pasted image 20251007155322.png]]

Converting quantifiers:
![[Pasted image 20251007155919.png]]