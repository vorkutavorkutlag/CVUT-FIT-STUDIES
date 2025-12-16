[[COURSES/BIE-DML/LECTURE 20|LECTURE 20]]
$gcd(a,b) = gcd(b,a)$ 
Also, since it's a positive number,
$=gcd(|a|, |b|)$ 
Also,
$=gcd(a, b+ka)$
Another property
$gcd(a,0) = |a|$

There is a method to find the GCD of $a, b$ by forming the next matrix $$\begin{bmatrix}a & 1 & 0 \\ b & 0 & 1\end{bmatrix} \implies_{GEM} \begin{bmatrix}g & \alpha & \beta \\ 0 & * & * \end{bmatrix}$$
Then, $g$ will be our GCD, and $\alpha, \beta$ will be our Bezout coefficients for $a, b,$ respectively.

Note that we are working with integers, so we will be using integer division, keeping the greatest value on top, until the number on the bottom becomes zero.

This computation of GCD will be useful to compute any diophantine equation $ax+by=c$ where they are all integers.
It has a solution $\iff gcd(a,b) | c$

Moving onto modular arithmetic, let's try solving $4^{44} \mod 13$ 
How can we find the number between 0-12 corresponding to that number?
We will obviously not be using direct computation.
We can use linear multiplication, where $4^{44} = 4*4*4*4...*4$ (44 times, $\mod 13$)
$4*4=16=3...*4=12...*4=...$
Also not that quick.
We may use Square & Multiply.
The idea is that 44 can be written as a sum of powers of two. $44=32+8+4$ 
That means, $4^{44} = 4^{32}*4^8*4^4$ 
$4^1=4, 4^2=3, 4^4=3*3=9, 4^8 = 9*9=3, 4^{16}=3*3=9, 4^{32}=9*9=3$
We build it from the bottom-up, and then plug it into our powers.

We can do better. If our modulo is a prime number, we may use $LFT$, Little Fermat's Theorem.
If $p$ is prime, $a^{p-1} \equiv 1 \mod p$
We want to write $44$ as $12*3+8$, then $4^{44} \equiv (4^{12})^3 *4^8 \equiv 1^3 * 4^8 \equiv 4^8 \equiv 3$

Let us consider $13^{33} \mod 15$
if we use S&M, we may achieve $13^1 = 13, 13^2 = 4$ which is easy to compute, since we may 'cheat' and represent $13 \mod 15$ as $-2 \mod 15$ and square it. $13^2 = (-2)^2 = 4$
We keep going from the bottom up, using the previous result to compute the next power.

We cannot use $LFT$ here as 15 is not prime, however, we can use Euler's Theorem for this.
When we have equation $a^b \mod c$ 
If $gcd(a, c)=1$, then $a^{\phi(c)} \equiv 1 \mod c$  Where $\phi(c)$ is the number of coprimes with $c$.
As in, the number of coprimes up to that number, including.
If $p$ is prime, then $\phi(p) = p-1$
Additionally, $\phi(p^\alpha) = p_\alpha (1- \frac{1}{p})$ 

If two numbers are coprimes, $\phi(ab) = \phi(a) * \phi(b)$
For example, $\phi(15) = \phi(3*5) = \phi(3) * \phi(5) = 2 * 4 = 9$
Additionally, every number can be written as a factorization of primes. Therefore, we may find the $\phi$ evaluation of every prime separately and do the product.

$\phi(m) = m * (1-\frac{1}{p_1})(1-\frac{1}{p_2})...(1-\frac{1}{p_n})$

When we cannot use $LFT$ nor Eulers's Theorem, we are forced to use linear multiplication and S&M. Unless....
Homework: Rewrite $360240142^{123} \mod 120$  as a system of congruences.
Then use Ch.R.Theorem.

A system of linear congruences is an SLE with a single variable in modulo. For example,
$2x\equiv 3 \mod 5$
$3x \equiv 4 \mod 7$
$5x \equiv 7 \mod 11$
We may form a diophantine equation out of each one of those.
For example, $2x=3 \mod 7$
Then, $2x+7(-k)=3$
We check for a solution by $gcd(2,7)=1|3$
Then, $1 = (-3) * 2 + 1*7 \implies 3 = -0 * 2 + 3 * 7 \implies 2 * -9 = 3 \mod 7 \implies x = -9 \equiv 5 \mod 7$ 
Though the entire set of solutions is $\{5+7k : k \in Z\}$ 

We also have an algorithm.
$x \equiv a_i \mod m_i$ for $i=1,2,...$
if $gcd(m_i, m_j) = 1$ then we have a unique solution $\mod m$ and this solution is given by
$x = \sum_i a_i x_i M_i \mod M$ where $M = \prod m_i$ and $M_i = \frac{M}{m_i}$ and $M_i x_i \equiv 1 \mod m_i$ 

For $x \equiv 2 \mod 5 x \equiv 1 \mod 3$ 
$a_1 = 2, m_1 = 5, M_1 = 3$
$a_2 = 1, _2 = 3, M_2 = 5$
$3x_1 = 1 \mod 5 \implies x_1 = 2$
$5x^2 \equiv 1 \mod 3 \implies x_2 = 2$
$x=2*2*3 +1*2*5 \mod (3*5) \equiv 7 \mod 15 \implies \{7+15l : l \in Z \}$
This is Chinese Remainder Theorem Ch. R. Theorem.
There also a generalized version using LCM if the GCD is not 1.
Though, we can use back-substitution.

$x \equiv 4 \mod 6 \implies x = 4 + 6k$
$x = 6 \mod 8 \implies 4 + 6k = 6 \mod 8 \implies 6k \equiv 2 \mod 8$
$3k \equiv 1 \mod 4 \implies k = 3 \mod 4 \implies k = 3+4l$
Then, $x=24l+22$

...Say we also know $x = 22+24l \equiv 10 \mod 20$
$\implies 24l \equiv -12 \mod 20$
$\implies 4l \equiv 8 \mod 20$
All multiples of 4.
$l \equiv 2 \mod 5 \implies l = 2 + 5h$
Then, $x=22+24(22+5h)=70+120h$

Thus, set of solutions $\{70 + 120: h \in Z\}$ unique solution between $0$ and $119$
Infinitely many solutions since we may change $h$ as we want.

We can use Ch.R.Thm when the GCD of every pair of the modulo's is 1.


Moving onto cardinalities.
Infinite sets can have the same cardinalities. For example,
$|N| = |N \times N|$
We find it by drawing a matrix of the cartesian product.
Diagonals from right to left top to bottom.
Then we enumerate, and map every natural number to every tuple.

Onto relations.
Relations can be reflecting. $a=b \implies b = a$
Relations can be transitive. if $x > y$ and $y > z$ then $x > z$
The can be symmetric, asymmetric, etc.