
A field is a set in which you may have addition and multiplication, elements that behave like 1 and elements that behave like 0. Let F be a set with two operations called addition an multiplication. We write the addition of a ∈ F and b ∈ F as a+b and the multiplication of and b as ab.
If the following conditions hold for all a, b, c ∈ F then F is called a field:
Commutativity
Closure
Associativity
Zero element
Additive inverse
Closure under multiplication
Commutativity of multiplication
Associativity of multiplication

There is a unit element 1 ∈F such that 1a = a
If a $\ne$ 0 (NON-ZERO) there is a multiplicative inverse $\frac{1}{a}$ ∈ F such that $a\frac{1}{a}$ = 1
Distributivity holds up: a(b+c) = ab+ac
Real numbers R, Complex numbers C, Rational numbers C all count as fields.
On the contrary, Natural numbers N are not a field because they contradict at least one of the necessary conditions. 
The sum and product of integers is integers, but we do not have a zero element in N, meaning 0 + a = a cannot exist, and therefore N is not a field.

...
The unit element of a two dimensional matrix is 
[1, 0]
[0, 1]
Multiplied by any other matrix, you get the same matrix.

We have a multiplicative inverse if there is such a matrix C such that AC = $1_2$
Though, this doesn't always hold, so matrices cannot be fields.



Let P be a prime number.
(Cannot be divided by anything else other by itself and `1`. Example: 2, 3, 5, 7, 11, 13, 17.)
It will be useful later on to maintain the property of the field
Let $Z_p := \{[0]_p, [1]_p,...[p-1]_p\}$
We want to define addition, multiplication.
Addition: $[a]_p +_p [b]_p = [a+b mod p]$ 
Multiplication: $[a]_p *_p [b]_p = [ab \mod p]$
If $a+b = rp+s$, then  
Examples:
$3+2 \equiv 0 \mod 5$
$4+7 \equiv 2 \mod 3$        ($3*3=9$ and $11-9=2$)
The remainder should be between 0 and p-1. 

When we have a modulus set, we can use its cyclic properties to define it as a field.
The additive inverse of $[a]_p$ is: $[p-a]_p + [a]_p = p \mod p = [0]_p$

The modulus will be used to solve SLE in the future.

the multiplicative inverse of $[a]_p^-1$ is $[a]_p^1$ and they are equal to one another in this field.
This only holds up in prime numbers, as opposed to any other sets. p must not be written as m, n.