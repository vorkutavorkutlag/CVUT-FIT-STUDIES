
Topics in an arbitrary order.

__Greatest Common Divisor (gcd)__

It is the greatest single factor of two numbers $a,b$ denoted $gcd(a,b)$
There are different theorems and formulas to find it, but I will be using the matrix one.

Augment matrix $\begin{bmatrix}a & 1 & 0 \\ b & 0 & 1\end{bmatrix}$ and proceed to do Gaussian Elimination on it, always swapping rows until the smaller pivot is at the bottom. 
Eventually, you will end up with $\begin{bmatrix}0 & * & * \\ d & e & f\end{bmatrix}$ where $d$ will be the result of $gcd(a,b) = d$, and $e, f$ will be the Bezout coefficients respectively.
The first coefficients will correspond to the top number in the beginning of the process, whereas the second number will correspond to the bottom number in the beginning of the process.
Bezout coefficients are defined such that $ea+fb=d=gcd(a,b)$ 

The least common multiple (**lcm**) is found through $$lcm(a,b) = \frac{|a| \cdot |b|}{gcd(a,b)}$$
__Diophantine Equations__

A linear Diophantine equation $$ax+by=c$$has integer solutions iff $gcd(a,b)|c$
If there is a solution, there are infinitely many solutions given by:
$$x=x_0+\frac{b}{gcd(a,b)} \cdot t, \ y=y_0 - \frac{a}{gcd(a,b)} ~~~~t \in Z$$
The first solutions will be $x_0 = a \cdot \frac{c}{gcd(a,b)} ~~~ y_0 = b \cdot \frac{c}{gcd(a,b)}$

__Modular Arithmetic__

It's when we have modulo and stuff. Like a clock. We've been over this.

To find the additive inverse of a number $a$ in $\mod n$, we find $n-a$.
To find the multiplicative inverse of a number $a$, we first must assure it exists. It exists only when $a, n$ are co-prime - as to say $gcd(a,n)=1$, as to say, they are prime with relation to one another.
Then we may either brute force it by testing the numbers in $Z_n$ one by one, or we could use the equation $a \cdot x + n \cdot k = 1$ where $k$ is an arbitrary integer, $x$ is the inverse of $a$. Numbers $x$ and $k$ can be obtained by the Bezout coefficients of $gcd(a,n) = ax+ky = 1$ where then $a^{-1}=k$ .

To calculate powers in a given modulus, i.e. $3^{33} \mod 11$, may employ several methods.

__Linear Multiply__: 
Naive. Just multiply manually... Never!
__Square and Multiply__: 
Divide into powers of 2. For example, $3^{33}=3^{32} \cdot 3$ 
Then, we find $3^{32}$ by squaring $3$ over and over in modulo.
__Euler's Theorem / Fermat's Little Theorem__:
Applies only when the modulo is prime. 
Then, FLT states $a^{n-1} \equiv  1 \mod n$ 
This can be used to split into the closest $n-1$ exponent, which simplifies the term.
__Negation Trick__ 
It's useful to look at the base sometimes. For example, in $\mod 15$, if the base is $14$, it is much easier to take its negation, begin $-1$ . Then, we see that every odd power of $14$ is just $14$, and every even power of $14$ is $1$.

To solve a linear congruence we employ first the theorem, saying that for $ax \equiv b \mod m$, given $d = gcd(a,m)$, if $d \nmid b$ there is no solution, but if $d \mid b$ there are exactly $d$ solutions $\mod m$.
Then, to solve, we divide the entire congruence by $d$, and then find the multiplicative inverse of the coefficient.
Then, to solve a series of linear congruences, we employ Chinese Remainder Theorem.
If all moduli are coprime, then a unique solution $\mod M = m_1m_2...m_k$ exists.
Otherwise, solutions exist iff $a_i \equiv a_j \mod gcd(m_i, m_j)$ for all $i, j$.

For exams, you should solve each congruence into form $x \equiv r \mod m$.
Combine two congruences at a time. Reduce to a single congruence. Repeat.

For example, for $x \equiv 2 \mod 5$ and $x \equiv 1 \mod 3$, the gcd is 1, so we find values that are congruent to 2 in mod 5, and then check them in mod 3, if they satisfy.
Then, we multiply the moduli, getting $x \equiv 7 \mod 15$.

__Division Algorithm__ states that for every integers $a,d$ where $d$ is nonzero, there exist unique integers $q,r$ such that $a=qd+r$. 
Additionally, it holds $q = a \div d$ , $r = a \mod d$ 


__Definitions___
Divisibility a|b is defined as $(\exists k \in Z) b = ka$
The division algorithm states that for every two numbers c, d, it is possible to represent c as $qd+r$ where $q = d \div c$ and $r = d \mod c$

A linear diophantine equation follows form of $ax+by=c$ where $a,b,c$ are known and $x,y$ are unknown variables. All of these are integers.
To solve it, use EEA, to find Bezout's coefficients s.t. $gcd(a,b)=Aa+Bb$
After some algebra, we see may find a particular solution, s.t. $$x=A\frac{c}{gcd(a,b)}~;~y=B\frac{c}{gcd(a,b)}$$
Then, for every other solution, we have the complete set of solutions
$$\{x_0+\frac{b}{gcd(a,b)}k, ~~y_0 - \frac{a}{gcd(a,b)}~:~k \in Z\}$$

The definition of congruencce for numbers $a,b,m$. We say that $a$ is congruent to $b$ modulo $m$ and we write $a \equiv b \mod m$ iff $m|(a-b)$.
As in, $\exists k \in Z$ s.t. $a=b+km$ 
The congruence $\mod m$ is an equivalence relation on $Z$.

The multiplicative inverse in modular arithmetic can be found only when the GCD of the modulus and our target inverse is 1. Otherwise it does not exist.
We may divide the entire expression by our gcd, if the other variables are divisible, and keep solving it as such. Otherwise, congruence has no solution.
After dividing the expression, we use the new expression from that moment onward to the end of the question.

According to Fermat's Little Theorem, if $p$ is prime and $a$ is not a multiple of $p$, $a^{p-1} \equiv 1 \mod p$

Euler's Totient Function $\Phi$  counts the number of positive integers less than or equal to $n$ that are coprime with it. By theorem, $\Phi(p) = p - 1$ if $p$ is prime.
For any power of a prime, $\Phi(p^a) = p^a - p^{a-1}$
For non-prime numbers, we use the canonical prime factorization of the number.
$\Phi(n)=n(1-\frac{1}{p_1})(1-\frac{1}{p_2})...(1-\frac{1}{p_k})$

A linear congruence $ax \equiv b \mod m$ only has a solution iff $gcd(a,m)|b$
All its solutions are of form $x_0 + k \cdot \frac{m}{gcd(a,m)}$ where $k$ is an integer.
Moreover, there is some $y_0$ such that the pair is a solution of diophantine equation $ax+my=b$.
