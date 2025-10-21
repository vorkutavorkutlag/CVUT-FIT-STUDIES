[[COURSES/BIE-DML/LECTURE 9|LECTURE 9]]
### Predicate Logic

Still using the same formulas and connectives we've used in propositional logic, but we are expending with other terms. For example, with the use of constants (numbers, objects), variables (x, y, a, b), quantifiers (for every x, there exists y). We may create terms from the existing terms using functions (input and output). Formulas are obtained by combining terms, quantifiers and functions into predicates.

When a formula does not contain any other piece of sub-information we call it an atomic formula. $z=y$ is an atomic formula, whereas $(z=1)\lor(z=y)$ is not an atomic formula. It is a formula, but not an atomic formula.

function: terms -> terms
predicate: terms -> formula

Predicates that take only one element are called unary predicates, as their arity is 1.

The topic of complete sets exists her as well in the form of functions. There a complete sets of functions with which it is proven that you may express any other formula. For example, to express $n \leq y$ , may be rewritten as $(\exists z)(y=n+z)$ .
Likewise, $n < y$ may be rewritten as $(\exists z)(y=x+z)\land \neg(x=z)$.
Note, we cannot write inequality in this example, so we use the negation.

"x is even" = $(\exists z)(x=z+z)$
"x is odd" = "not (n is even)" = $\neg(\exists z)(x=z+z)$ = $\forall(z)(\neg(x=z+z))$

"x=1" = $(\forall a)(a * x = a)$
"x=2" = $(\forall a)(a * x = a + a)$

"x is a composite number" = $(\exists a)(\exists b)(x=a*b) \land \neg(x=a) \land \neg (x=b)$
"x divides y" = $(\exists z)(y=x*z)$

"p is a prime number" = "p is not a composite number" = $\neg (\exists a)(\exists b)(x=a*b) \land \neg(x=a) \land \neg (x=b)$
$\equiv (\forall a)(\forall b)(\neg(x=a*b) \lor (x=a) \lor (x=b))$
$\equiv (\forall a)(\forall b)((x=a*b) \implies ((x=a) \lor (x=b)))$
This is almost correct. The number "1" is not prime. Therefore
$\neg (\forall c)(x*c=c) \land (\forall a)(\forall b)((x=a*b) \implies ((x=a) \lor (x=b)))$


To make specific quantifiers, let's look at a couple of examples.
$t(n)$ = "n is a book on the table".
"There is at least one book on the table": $(\exists b)t(b)$
"There is exactly one book on the table": $(\exists b)t(b) \land (\forall y)(t(y) \implies (b=y)$
"There are at least two books on the table": $(\exists b)(\exists c)(t(b)\land t(c)\land \neg (b=c))$
"There is at most one book on the table": $(\exists b)(t(b) \land (\forall y)(t(y) \implies (b=y)) \lor (\forall c) \neg t(b)$
Likewise, $(\forall b)(\forall c)((t(b) \land t(c)) \implies (b=c))$


