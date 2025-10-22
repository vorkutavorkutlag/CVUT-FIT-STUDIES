[[LECTURE 10 (TUTORIAL) - PART 2]]
Continuing exercises in predicate logic.

Given the example:
x is a a person from a range of people.
f(x) is a predicate which evaluates if a person can speak French
s(x) is a predicate which evaluates if a person can speak Spanish

1. "Somebody speaks French and somebody speaks Spanish"
$(\exists x)f(x) \land (\exists x)s(x)$

2. "Somebody speaks French and Spanish (same person)"
$(\exists x)(f(x) \land s(x))$

Sidenote, in this case, the latter formula logically entails the former.

3. "Somebody speaks French or somebody speaks Spanish"
$(\exists x)f(x) \lor (\exists x)s(x)$

This formula is a logical consequence of formula 1.

4. "Somebody speaks French or Spanish"
$(\exists x)(f(x) \lor s(x))$

According to the distributivity of quantifiers, this is logically equivalent to formula 3.



We have the following formulas:
$B: (\forall x)(\exists y)(p(x,y) \land \neg q(x,y))$
$C:\neg(\forall x)(\forall y)(r(x) \land (p(x,y) \implies q(x,y)))$
Pushing the negation inside, 
$C: (\exists x)(\exists y)(\neg r(x) \lor (p(x,y) \land \neg q(x,y)))$

In order to find out which formula entails which, we must look at the entailment with quantifiers. i.e. $(\forall x) A \vDash (\exists x) A$ and not the other way around. If everyone is smart, then at least someone is smart. If at least someone is smart, it does not mean everyone is smart.
Additionally, because of the disjunction inside C, this points toward:
$B \vDash C$ 
$(\exists y)(F(x,y) \vDash (\exists y)(\neg r(x) \lor F(x,y)) \vDash (\exists x)(\exists y)(\neg r(x) \lor F(x,y))$


Another example:
Consider a set of animals with one unary and two binary predicates: 
h(x) - "x is a herbivore", p(x, y) - "x hides from y", r(x, y) - "x runs away from y".

1. "Every herbivore runs away from someone or hides from someone":
$(\forall x)(h(x) \implies (\exists y)(p(x,y) \lor r(x,y)))$

2. ...
3. "It is not true that someone runs from no one"
$(\forall x)(\exists y)r(x, y)$
4. ...
5. "None of those who run away from no one are herbivores."
$(\forall x)(\forall y)(\neg r(x,y) \implies \neg h(x))$

$A \lor B \vDash A \lor B \lor C$
therefore 
$F_5 \vDash F_1$
$F_3 \vDash F_5$

