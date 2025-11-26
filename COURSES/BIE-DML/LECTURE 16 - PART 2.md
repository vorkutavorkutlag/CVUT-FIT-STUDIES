[[LECTURE 16 - PART 3]]
# Number Theory
Divisibility, GCD, EEA
Diophantine Equations, Modular Arithmetic

Number Theory is a part of mathematics that deals with numbers and their properties. One of the oldest branches of math, formulated and solved before Christ. Some classical results include that there are infinitely many prime numbers, and square root of two is not a rational number.


##### Division
One of the important properties of integers is that we can divide them with zero remainder by other integers. The definition of divisibility is as follows.
Let $a, b \in Z$. We say that a divides b, denoted by $a|b$, if there is a $k \in Z$ such that $b = ka$
If this does not hold, we write that $a\not | b$
1 divides every number, every number divides itself, every number divides zero, and zero divides itself.
It does not mean we can divide by zero. However, the definition is a relationship between two numbers. $0 = k * 0$ holds for any $k \in Z$.

Let us list a few simple properties of divisibility.
Let $a, b, c \in Z$
$a|b \land a|c \implies a|(b+c)$
$a|b \implies a|(nb) \forall n \in Z$
$a|b \iff |a|$ | $|b|$
$a|b \land b \neq 0 \implies |a| \leq |b|$ 
$a|(b+c) \land a|b \implies a|c$
$a|b \land a|c \iff a|(mb+nc) \forall m,n \in Z$
The proofs are trivial.

According to The Division Algorithm...
Let $a, d \in Z \land d > 0$. Then there exist unique $q, r \in Z$ s.t. $$a = qd+r \land 0 \leq r \leq d$$
In the equality given by the theorem above, we call $d,a,q$ and $r$ divisor, dividend, quotient and remainder respectively. We write 
$q = a \div d$ (integer division)
$r = a \mod d$
The existence of $q, r$ for arbitrary $a \geq 0$ is proved by mathematical induction on $a$.
Likewise, we can do induction again but in the opposite direction, $a \leq 0$

### Common Divisor, Common Multiple, GCD, LCM
Let $a, b \in Z$. We say that:
- $d \in N_0$ is a common divisor of $a, b$ if $d|a \land d|b$
- $d \in N_0$ is the greatest common divisor (GCD) of $a, b$ if:
$$d|a \land d|b \land (\forall n \in N_0)((n|a \land n|b) \implies n|d)$$
Every subsequent divisor divides our divisor d.
We define it as $gcd(a, b) = d$.
$a, b$ are co-prime if $gcd(a, b) = 1$

- $m \in N_0$ is a common multiple of $a, b$ if $a|m \land b|m$
- $m \in N_0$ is the least common multiple (LCM) of $a, b$ if:
$$a|m \land b|m \land (\forall n \in N_0)((a|n \land b|n) \implies m|n)$$
Some properties of GCD and LCM are as follows.
$gcd(a, 0) = a$, $lcm(a, 0) = 0$
$gcd(a,b)=gcd(|a|,|b|)$,  $lcm(a,b)=lcm(|a|,|b|)$
$gcd(a,b)=gcd(b,a)$, $lcm(a,b) = lcm(b,a)$

Auxiliary Lemma for Euclid's Algorithm.
Let $a, b \in Z$. Then, for every $c \in Z$, $gcd(a+cb, b) = gcd(a,b)$
As a corollary, if $a = qd+r$ is the identity, we know that $gcd(a,d) = gcd(qd+r, d) = gcd(d,r)$

**Euclid's Algorithm**
The algorithm of finding GCD of two natural numbers was originally formulated by Euclid (approx 350 BC). Today we refer to it as the Euclidean Algorithm.

Let $a, b \in Z$ such that $a \geq b > 0$. We define the following sequence of remainders recursively.
$r_0 = a$, $r_1 = b$
$\forall n \geq 2: r_n = r_{n-2} \mod r_{n-1}$

$\implies r_{n-2} = q_{n-1}r_{n-1} +r_n$
Then, $(r_n)_{n \geq 0}$ is decreasing and there is finite $k \in N$ such that $r_{k+1} = 0$
The last non-zero remainder $r_k$ is equal to $gcd(a,b)$

**Bezout's Identity**
The GCD can be written as an integer linear combination.
Let $a, b \in Z$
$(\exists m,n \in Z) (gcd(a,b) = ma + nb)$
In the above equality, we call m and n the Bezout's Coefficients of a and b.

It is possible to find the coefficients using EEA (Extended Euclidean Algorithm)
