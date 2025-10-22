
A couple of proofs to practice how to prove using direct and indirect proof.

Let m, n, p, be integers.
If m+n and n+p are even, then m+p is even.
        A                                      B
If we were to formalize it, it means that for every m, n, p that are integers. Therefore, we will be using the for-all quantification. $(\forall m,n,p \in Z)$
The premise, assumption, hypothesis is that m+n and n+p are even.
What we want to prove is that m+p is even.

m,n,p are arbitrary integers without any conditions.
m+n is even and n+p is even
$(\forall m,n,p \in Z)$

$(\exists k \in Z) m+n=2k \land (\exists l \in Z)(p+n=2l)$
$\implies (\exists k, l \in Z)(m+n+n+p = 2k+2l)$
$\implies (\exists k,l \in Z)(m + p = 2(k+l-n))$
$\implies$ m+p is even

This was a direction proof.


Now, for an indirect proof, using the contraposition law. 
$A \implies B \equiv \neg B \implies \neg A$

Let m,n,p be positive integers.
if $p = m*n$ then $m \leq \sqrt p$  or $n \leq \sqrt p$ 
     A                            B
After negating B, A
$m > \sqrt p \land n > \sqrt p \implies p \neq m * n$
$m > \sqrt p \land n > \sqrt p \implies m * n > \sqrt p * \sqrt p \implies m * n > p$
$\implies p \neq m * n$

To know what type of proof to use, you try one thing, and if you get stuck or fed up you go to try a different method. There is no a method of knowing exactly what type of proof exactly to use for each problem, it is a creative progress that requires some intuition and practice.

Another example:
Let a,b,c be positive integers
If a divides b and b divides c then a divides b+c

The proof for:
$(\exists k, l, j \in N)$
$(b = k * a) \land (c = l * b) \implies (b+c = j * a)$ 
	hypothesis           conclusion

Is as follows:
$(\exists k, l, j \in N)$
$(b = k * a) \land (c = l * b) \implies (b = k * a) \land ( c = l * k * a)$
$\implies (b + c) = (k * a + l * k * a) \implies (b + c) = (l+2*k)a$
$\square(b+c) = (j * a)$ 