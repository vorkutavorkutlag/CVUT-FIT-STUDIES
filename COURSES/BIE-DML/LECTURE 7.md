[[COURSES/BIE-DML/LECTURE 7 - PART 2|LECTURE 7 - PART 2]]
## Finishing Predicate Logic

Let's assume that quantifiers always take precedence than other logical connectives. For example, $(\forall x)p(x) \lor q(x)$ means $((\forall x)p(x)) \lor q(x)$ .
It is different from $(\forall x)(p(x) \lor q(x))$.
If it is without brackets then it means the former, only applying to $p(x)$.

#### Quantifier Exchange
For any formula of predicate logic A(x), where x is free in A,
$(\forall x)A(x) \vDash A(x) \vDash (\exists x)A(x)$
$(\forall x)A(x) \vDash A(c) \vDash (\exists x)A(x)$
where c is a constant and A(c) denotes a formula in which all occurrences of x are replaced by c.
For example, in the domain of N, A(x) means x > 0.
$(\forall x)A(x)$ means "every natural number is greater than 0".
$A(x)$ means "the number x is greater than 0".
$(\exists x)A(x)$ means "some natural number is greater than 0".
$A(1)$ means "the number 1 is greater than 0".

Logical consequence and logical equivalences have several properties between formulas.
Let E(x), F(x), G be formulas of predicate logic and assume that $E(x) \vDash F(x)$ then:
- $E(x) \lor G \vDash F(x) \lor G$ and $E(x) \land G \vDash F(x) \land G$.
- $(\forall x) E(x) \vDash (\forall x)F(x)$
- $(\exists x)E(x) \vDash (\exists x)F(x)$


For any formula of predicate logic A,
$$\neg (\exists x) A \equiv (\forall x) \neg A$$
$$\neg (\forall x) A \equiv (\exists x) \neg A$$
This is like the 'de morgan' of predicate logic.
"It's not the case that there exists a natural number smaller than 0" is logically equivalent to
"all natural numbers are greater than or equal to 0"

__To express "exactly one", "at most one", "or at least one'"__:

$(\exists x)m(x)$ means that there is at least one. It exists, could be more that one.

To say there is exactly one:
$(\exists x)(m(x) \land (\forall)y(m(y) \implies (y=x)))$
If we find 'another' truth valuation, it necessarily has to be the same one as the single one.

To say there is at least two:
$(\exists x)(\exists y)(m(x) \land m(y) \land \neg(x=y))$
There exist at least two valuations and it is guaranteed that they are not equal.

For example, to say '0' is the only truth valuation:
$m(0) \land (\exists x)(m(x) \implies (x=0))$
A combination of 'only one' and the specific truth valuation.


#### Quantifier Distribution

For every A, B formulas of predicate logic:
$(\forall x)(A \lor B) \equiv (\forall x)(A) \lor (\forall x)B$
$(\exists x)(A \lor B) \equiv (\exists x)(A) \lor (\exists x)B$


Also:
$(\forall x) A \lor (\forall x) \vDash (\forall x)(A \lor B)$
If "all students like maths or all students like physics" then
"all students like maths or physics"


Additionally,
$(\exists x)(A \land B) \vDash (\exists x)A \land (\exists x)B$
If "some student likes maths and physics" then 
"some student likes maths and some student likes physics"

![[Pasted image 20251014150654.png]]
![[Pasted image 20251014150704.png]]



Logical equivalence and logical consequence:
![[Pasted image 20251014151303.png]]

f                                          ff 