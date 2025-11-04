[[COURSES/BIE-DML/LECTURE 12|LECTURE 12]]
## Mathematical Induction

In the world of mathematics, there are a variety of different methods of proofs. Those include direct proofs, indirect proofs (contraposition / inverse implication), proof by contradiction, etc.

An example for a proof by contradiction.
The sum of an irrational number and a rational number is irrational.
$\forall x \in RQ, q \in Q \implies x + q \in RQ$
a number is rational when you can write it as $\frac{a}{b}$ where a, b are integers and b is nonzero.
Let suppose, by contradiction, the sum is rational.
$x+q \in Q \iff a, b \in Z, b \neq 0$ such that $x+q = \frac{a}{b}$
$q \in Q \iff m, n \in Z, n \neq 0$ such that $q = \frac{m}{n}$
$x+q-q = \frac{an - bm}{bm}$
but then, we show that x is rational, since it evaluates into a ratio of integers, which contradicts our hypothesis. Therefore, the opposite is true.

An example for proof by cases.
For any real numbers a, b, $|a| * |b| = |a * b|$
We know that $|x|$ is equal to x when $x \geq 0$, otherwise equal to -x
Case 1: $a \geq 0, b \geq 0$
$|a|$ = a, $|b|$ = b, $|a * b| = a * b$
$|a| * |b| = a * b = a * b = |a * b|$
Then, do it for all possible cases (4)
If it upholds for every case, then it is true for every possible real number a, b.


In a situation in which we have an infinite amount of cases, when they are nicely ordered, we may use the principle of weak induction.
Let's suppose that $A_0$ is true. Also, $(A_0 \implies A_1)$ . This implies $A_1$
Let's also suppose that $(A_1 \implies A_2)$ . This, then, implies $A_2$
$A_0 \land (A_0 \implies A_1) \land (A_1 \implies A_2) \land ... \land (A_{n-1} \implies A_n) \implies A_n$

If we manage to prove $A_0$, and also manage to prove $\forall p \in N (A_p \implies A_{p+1})$ , as a logical consequence: $\forall m A_m$
We simply need to prove two conditions. 
An initial condition, and a general condition for every subsequent propositional index. 

Let's prove that $\forall m \in N_0$  $z | m^2 -m$ 
Note, this symbol means:
$a | b \iff \exists k \in Z, \ b = a * k$ 
BS (Basis Step): $0^2 - 0 = 0 = 2 * 0 \implies 2 | 0^2 - 0$

Next, we want to prove
IS (Inductive Step): $true \ m \implies true \ m+1$ 
Assume: $\exists k \in Z \ m^2 -m = 2k$ 
Then, $(m+1)^2 - (m+1) = m^2 + 2m + 1 - m - 1 = m^2 - m$ 
$\implies 2 | m^2 - m \land 2 | (m+1)^2 - (m+1)$ 
Given the previous index is divisible by 2, then the current index is also divisible.

In IS, we want to prove that if it is true for a certain number, then it is true for the following number. Do not fall for the trick that 'we want to prove it is true for every number', as that would be the final step. We mustn't skip this intermediary step.
We want to prove the implication of if m is true then m+1 is true.


Let's prove, by mathematical induction, the following:
$\forall m \in N$
$\sum_{k=1}^m k = \frac{m(m+1)}{2}$ 
BS: (for m=1) $\sum_{k=1}^1 k = \frac{1(1+1)}{2} = 1$ 
IS: Assume that $\sum_{k=1}^m k = \frac{m(m+1)}{2}$ 
Then, $\sum_{k=1}^{m+1} k = \sum_{k=1}^{m} k + m + 1$ = $\frac{m(m+1)}{2} + (m + 1) = \frac{(m+1)(m+1+1)}{2}$ 

Q.E.D,
$\forall m \in N$
$\sum_{k=1}^m k = \frac{m(m+1)}{2}$ 


