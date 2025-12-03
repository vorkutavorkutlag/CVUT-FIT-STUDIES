# Number Theory

6.3. ($\forall a \in z) (6|a) \iff (2|a \land 3|a)$
Since this is an equivalence of two statements, we will use the approach that we can prove the equivalence if we can prove two implications.
- LHS implies RHS
- RHS implies LHS
Once we have proven both of these implications, we have proved the equivalence.

First, we take some $a \in Z$; $6|a \implies (2|a \land 3|a)$
$6|a \implies (\exists k \in Z) = a = 6k$
$\implies a=2*3*k$
$\implies a = 2 * (3k)$
$\implies a = 3 * (2k)$
Where $(3k) \in Z \land (2k) \in Z$ 
$\implies 2|a \land 3|a$

Then, we take some $a \in Z$; $(2|a \land 3|a) \implies 6|a$
$2|a \land 3|a \implies (\exists k, l \in Z) a=2k \land a=3l$
$\implies a = 2k = 3l$
$\implies 3 | 2k \land gcd(2,3) = 1$                       // since 2, 3 are coprime
$\implies 3|k \implies (\exists j \in Z) (k=3i))$
$\implies a + 2*3*j = 6*j$
$\implies 6|a$

Q.E.D $6|a \iff 2|a \land 3|a$

Theorem that we used:
$(a|bc \land gcd(a,b)=1) \implies a|c$ 


Let us practice extended Euclid's algorithm to find the GCD of two numbers.
6.6.a. $a = 420, b=231$
Find the GCD, and find the linear combination such that $420m + 231n = gcd(420,231)$
Those being the Bezout's coefficients
We begin with the initial LC.
$420 = 1 * 420 + 0*231$
$231 = 0 * 420 + 1 * 231$

$420 = 1*231 + 189$
$189 = 1 * 420 + -1 * 231$

$231 = 1 * 189 + 42$
$42 = -1 * 420 + 2 * 231$

$189 = 4 * 42 + 21$
$21 = 5 * 420 + -9 * 231$

$42 = 2 * 21 + 0$

So, to sum this up, we know $gcd(420,231)=21$ and $420 * 5 + 231 * (-9) = 21$


Let's look at some simple diophantine equations now.
What is a linear diophantine equation?
$ax+by=c$ Is a linear diophantine equation $\iff a,x,b,y,c \in Z$
A diophantine equation has a solution $\iff gcd(a,b) | c$
For example, $2x+4y=3$ has no integer solution.

Though $3x+6y=9$ has a solution since $gcd(3,6)=3 \land 3|9$
Let us divide then by GCD, achieving $x+2y=3$
For example, $(1,1)$ belongs to the set of solutions
Let us now equal to zero.
$x+2y = 0 \implies 1x= -2y$ and 1, 2 are coprime
$x=2k, k \in Z \implies 2k = -2y \implies y = -k$
Therefore, $(x,y) = (1,1)+(2k,-k) k \in Z$
For the first step, just any solution we can find will do.


6.11. Find $-a, a^{-1}$ for $a \in Z_n$ 
$n=42$, $a=25$
Now, set $Z_{42} = \{0, 1,...,41\}$
The multiplicative inverse exists only for some numbers.
Any number which is not coprime with 42 will not have an inverse.
That is why in LA1 we use exclusively prime modulus.
In the case of the additive inverse, we want a number in the set whose addition will result in zero. $-25=17$ since $17+25=42=0$

Now multiplicative inverse, here we find a number in the set whose multiplication will result in one $25 * x = 1$ we can find it as the solution to $25x+42y=1$ 
The inverse element is the $x$ part of the solution of this diophantine equation.
$gcd(25,42)=1$ and $1|1$ so it has a solution.
The solution to the GCD and Bezout coefficients is: $25 * -5 + 42 * 3$
Therefore, $25 * -5 + 42 * 3 = 1$ is a solution.
Though, $-5$ is not the inverse, so we want to add 32 to get a number which is in the set.
$-5 + 42 = 37 \in Z_{42} \implies 25^{-1}=37$ in $Z_{42}$ 

Fermat's little theorem and Euclid's theorem were mentioned, presumably from the lecture I missed. Should check the lecture slides for more insight.
Tasks for example $6^{66} \mod 19$ will be using FLT $\implies 6^{19-1}=6^{18}\equiv 1 (\mod 19)$ 

Binary exponentiation / Square and Multiply
If nothing else works we can use this method.
Take the exponent, and write it as the sum of powers of two. $2^3+2^2$ 
$6^{12} = 6^8+6^4$ 
$6^2=36\equiv17\equiv-2\mod19$ 
$6^4=6^{2^2}\equiv(-2)^2=4\mod19$
$6^8=4^2=16\mod19$

If we have a number we may work with a smaller negative number.

Then we substitute then $4*16=64\equiv7\mod19$

Need to read up on Euclid Theorem's Phi function $\phi$ 