[[COURSES/BIE-DML/LECTURE 17 (TUTORIAL)]]
### Linear Diophantine Equations
We are visiting a strange country, where the coin values are 7 and 13 peso. How many coins of each value are needed to pay the amount of 125 peso?
This problem can be described by the equation $7x+13y=125$, whose solution for x and y should be found in the integer domain.

An LDE of two variables is any equation of the type: $$ax + by = c$$Where $a, b, c \in Z$ and $x, y$ are integer unknowns $\in Z$

Let's discuss the solvability of LDE.
The equation has a solution if and only if $gcd(a,b) | c$
We solve for the GCD and find the Bezout's coefficients accordingly. Then, we multiply the equations by the appropriate number to get a solution on the LHS. 

A lemma about GCD.
Let $a, b \in Z \land (a \neq 0 \lor a \neq b)$
$gcd(\frac{a}{gcd(a,b)}, \frac{b}{gcd(a,b)})=1$
Let $a, b, c \in Z$ if $a|bc$ and a, b are co-prime, then $a|c$

Let $a, b \in Z$ \ {0} and let $(x_0, y_0) \in Z^2$ be some solution of the equation $ax + by = c$.
Then, the set of all integer solutions is:
$$\{(x_0 + \frac{b}{gcd(a,b)} * k), (y_0 -\frac{a}{gcd(a,b)} * k): k \in Z\}$$
## Primes
The set of all natural numbers N can be partitioned into following three subsets according to the number of divisors. 
- The number 1, which is only divisible by itself.
- Primes, which are divisible by themselves and 1.
- The remaining numbers, which are called composites.

There are infinitely many primes.
It is proved by contradiction. showing that you may create a new prime out of previous primes.

Every composite number can be written as a product of primes.

**The Fundamental Theorem of Arithmetic**
Every n can be written in a unique way by a product of primes. It is called the canonical factorization of n, or prime factorization of n.
It has many applications. For example, it can be used to calculate both GCD and LCM of any pair of natural numbers a and b.
We rewrite prime factorization of both a and b in such a way that both factorizations contain the same k-tuple of primes with possible zero exponents..
Then we have $$gcd(a,b) = p_1^{min(a_1,b_1)} * p_2^{min(a_2,b_2)} ... * p_k^{min(a_k,b_k)}$$Then, similarly: $$lcm(a,b) = p_1^{max(a_1,b_1)} * p_2^{max(a_2,b_2)} ... * p_k^{max(a_k,b_k)}$$
