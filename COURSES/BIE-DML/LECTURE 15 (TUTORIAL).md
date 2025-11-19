As a reminder, 
a function is **injective** where every value is unique.
$\forall x, y \in A : f(x) = f(y) \implies x = y$
a function is **surjective** when there's a mapping for any number. image set = codomain
$\forall z \in B, \exists x \in A : f(x) = z$
A function that satisfies both is **bijective**.
If we want to prove that a property 'for every' is not true, you have to prove that there exists ... such that it is not the case. In simple words, we need to find a single counterexample.

Similar functions can have different behaviors according to their domains.
For example, mappings:
$f: Z \rightarrow Z : n \rightarrow n^3$ : injective, not surjective (cubic roots aren't integers)
f: $R \rightarrow R : n \rightarrow n^3$  : injective, and surjective

Another way to ask for surjectivity is, can we find a preimage for every element in the codomain?
It can often be proven through proof by cases. For example, mapping from $N_0 \times N \rightarrow Z$ such that $(m, n) \rightarrow m - n$ . We split it into $z > 0, z = 0, z < 0$
It is not injective, however, is surjective.

Two mappings can be composed into a single mapping.
$fog(x) = f(g(x))$
If $fog$ is surjective then $f$ must be surjective. Must $g$ be surjective?
We can use direct proof, or proof by contraposition.
Let's assume C is not surjective.
$\exists c \in C ; \forall b \in B :f(b) \neq c \implies$
$\exists c \in C ; \forall a \in A : f(g(a)) \neq c \implies$
$\exists c \in C ; \forall a \in A : fog(a) \neq c$
We have used proof by contraposition to prove mapping $g$ is surjective.

If $fog$ is injective then $g$ must be injective. Must $f$ be surjective?

The definition of cardinality is based of bijection. A cardinality of a finite site is the number of elements in the set. A set of days of the week has the cardinality of 7. With infinite sets, things become more complicated, but, we will skip those for later.

### Combinatorics

There are different ways we can count objects.
With n objects, we can count the ways we can arrange them in order. that would be $n!$
$n! = n (n-1)(n-2)...(2)(1)$
This is called permutations.
Variations without repetition, with a given number of 'slots' would be
$n (n-1) (n-2) ... (n-k+1) = \frac{n!}{(n-k)!}$
Allowing repetitions, for a given number of 'slots', would be
$n * n * n * ... * n =n^k$
Combinations without repetition: $\frac{n!}{(n-k)!k!}$ = $n \choose k$
Combinations with repetition: $n + k -1\choose k$
Permutation with repetition: $\frac{n!}{n_1!n_2!...n_k!}$


Let's suppose we want to count all the strings we can obtains using 0's and 1's that have length 8.
00000000, 00000001, 00000010, 00000011, and so on.
For each character, we have a choice to put either 1 or 0, so $2^8$ . Variations with repetition
To determine how many strings contain exactly 4 1's.
$8 \choose 4$ given by combinations without repetition.
To determine how many strings contain less than 4 ones.
${8 \choose 3} + {8 \choose 2} + {8 \choose 1} + {8 \choose 0}$  given by additive principle, saying when we want to count all objects with some property but we can divide it into sub-properties that have no intersections, we can count the sum. 
Similarly, there is the multiplicative principle, saying that if we have a certain number of things, and these numbers are multiplicative in the sense that the events are independent and it's giving you possible choices, and there is no intersection, we can multiply it.
The multiplicative principle is at play in the first exercise.

useful identities, easily proven:
${m \choose 0} = 1$, ${m \choose m} = 1$, $m \choose 1$ = 1, $m \choose m-1$ = m, $m \choose m -k$ = $m \choose k$ not being chosen is being chosen
$\sum_{i=0}^m {m \choose i} = 2^m$
$(a+b)^n = \sum_{i=0}^n {n \choose i} a^{n-i} * b^i$

For all the objects, we can either choose them or not choose them, it is a binary choice.

How many different strings do we have in 16 bits? $2^{16}$ 
How many of them start with 0011? For the first four, we only have one choice, no choice, the choice we were given, for the rest we have 2 choices (0 or 1). so $2^{12}$
How many of them will be a palindrome? We can freely choose the first half, and will have no choice, one choice, for the second half $2^8$ 
The actual function is $2^{\lceil n \rceil}$ . Where ceiling is the smallest integer greater than $n$
How many of them have 1 in the first or in the last bit?
We have 3 options. Starting with 1, ending with 1, starting with 1, ending with 0, starting with 0, ending with 1. $2^{14} + 2^{14} + 2^{14} = 3 * 2^{14}$ . Could not just use $2^{15} + 2^{15}$ as there will be overlap.
We could alternatively find the complement. Complement Principle.
If we know how to count all the elements, and the 'bad ones', then the 'good ones' are going to be the difference. That means, subtraction between all possible strings and the ones that have 0 in the beginning and the end. so $2^{16} - 2^{14}$
How many strings contain exactly two symbols 1?
We look for the positions where to put the ones. We are choosing 2 elements out of 16.
Therefore the answer is the combination $16 \choose 2$ 

Everything done with the binary alphabet can also be done with different alphabets.
Consider string of length 3 consisting of letters A, B, C, D, E.
How many distinct strings can be obtained if they can be repeated? $5^3$ multiplicative princ.
How many distinct strings can be obtained without repetition?  $\frac{5!}{(5-3)!}$
How many strings from a start with letter A? $1 * 5^2$
How many strings from b start with letter A? $1 * 4 * 3$
How many strings from b do not contain letter A? $4 * 3 * 2$ = $\frac{(5-1)!}{(5-1-3)!}$
How many strings from a contain letter A? Complement of strings that do not contain any A is $5^3-4^3$

Suppose we have 10 different books. 5 books about computers, 3 books about math, and 2 books about art.
In how many ways can we order these books on the shelf, not caring about order? $10!$
all computer books should be to the left and all art books to the right.
$5! * 3! * 2!$ Using multiplicative principle, not additive!
all books about computers should be to the left.
$5! * 5!$
the books of the same kind form a continuous group
$3! * 5! * 3! * 2!$
art books will not be placed next to each other
$({10 \choose 2} - 9*2) * 8!$ 
