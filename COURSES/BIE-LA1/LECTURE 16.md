[[COURSES/BIE-LA1/LECTURE 17 (TUTORIAL)]]
Finishing up determinant...
Particularly, computing determinants using permutations.
Theorem states $$det(A)=\sum_{\sigma \in S_n} a_{\sigma(1),1}a_{\sigma(2),2}...a_{\sigma(n),n}sgn(\sigma)$$
I have no idea what any of this means yet. Look at the lecture slides, or pray.

# Spectral Theory!
# Eigenvalues, Eigenvectors, Diagonalizability

We will need to compute the determinant for eigenvalues and eigenvectors.
There will not be a question to compute the determinant just on its own.
The same way there will not be a task to find the inverse of a matrix. However, we will need to compute it to get a change of basis matrix.

A polynomial is a mapping $p: R \rightarrow R$ of the form $p(x) = a_nx^n + ... + a_0$
Where $a_n...a_0 \in R$ are constants, called the coefficients of the polynomial.
The highest power of $x$ appearing in the polynomial, as long as its coefficient is not zero, is called the degree of the polynomial.
We can also have polynomials with coefficients in complex numbers $C$...

A degree-2 polynomial is called quadratic, a degree-3 polynomial is called cubic, and so on.

A root of the polynomial is a solution of the equation $p(x) = 0$
Geometrically, the roots of a polynomial are the $x$ values of the points where its graph crosses the $x$-axis.

If p is quadratic, then one method of finding the root is using the quadratic formula.
However, to find the roots of a polynomial with a higher degree, we will need more work.

### Polynomial Theorem (#1)
Let $p$ be a polynomial of form $p(x)=a_nx^n+...+a_0$
Where the coefficients are real numbers, and $a_n, a_0 \neq 0$

Every rational root of $p$ has the form $\frac{b}{c}$ where $b$ is a divisor of $a_0$ and $c$ is a divisor of $a_n$

### Factor Theorem
... Will be discussed in the tutorial.

### Fundamental Theorem of Algebra
Every non-constant polynomial has at least one complex root.

By combining the fundamental theorem of algebra with the factor theorem, we immediately see that every polynomial of degree $n$ has exactly $n$ complex roots that can be factored as $$p(x) = a_n(x-\lambda_1)...(x_n-\lambda_n)$$ Where $a_n$ is the coefficient of $x^n$ in $p$ and $\lambda_1 ... \lambda_nb$ are the potentially complex and not necessarily distinct roots of $p$.

To clarify, what we mean when we say that a polynomial has exactly $n$ not necessarily distinct roots, we need to introduce the multiplicity of a root $r$, which is the exponent of term $x - r$ in the factorization of the polynomial.
We think of a multiplicity-k root as one that "occurs k times", or as roots that are equal to one another.
With this in mind, the fundamental theorem of algebra says that every degree-n polynomial has exactly $n$ complex roots, counting multiplicity.
If $\lambda_1...\lambda_k$ are all mutually distinct roots of $p_A(\lambda)$, then there exist unique numbers (root multiplicities) $l_1,...,l_k$ such that $$p_A(\lambda) = a_n\prod_{i=1}^{k}(\lambda - \lambda_i)^{l_i}$$ and $l_1 + ... + l_k = n$

"For multiplicity, jut write it as a product and count the exponent."

"The later exam terms will be more difficult"


#### Eigenvalue
We say that $\lambda \in C$ is an eigenvalue of a matrix $A \in M_{n,n}(C)$ is and only if exists 
$v \in C^n \land v \neq \vec0$ such that $$Av = \lambda v$$ Vector $v$ is called an **eigenvector** of matrix $A$ corresponding to the eigenvalue $\lambda$ 
The set of all eigenvalues of $A$ is called **spectrum** of $A$ and denoted $\sigma(A)$
Hence the name, spectral theory.

Geometrically, we are seeing if that mapping of the matrix does not rotate $v$, and simply stretches or shrinks it, then that matrix is an eigenvector of the matrix, and the scalar by which is gets stretched or shrunk is the eigenvalue.

It is impossible to overstate the importance of eigenvalues and eigenvectors.
Everything we have learnt in the semester has been in preparation to this moment.

To find all the eigenvalues of a given square matrix (to kill a matrix)...
By the definition, $\lambda \in C$ is an eigenvalue of $A \iff$ $\exists x \in C^n \land x \neq \vec0$ such that$$Ax=\lambda x \equiv(A-\lambda I)x = \vec0$$ Therefore $\lambda \in C$ is an eigenvalue of $A$ $\iff$ SLE $$(A-\lambda I) x = \vec0$$ ...has a non-trivial solution. 
That is to say, more than one solution.
That is to say, matrix $(A - \lambda I)$ is not invertible
That is to say, $det(A - \lambda I) = 0$
Therefore, we have the theorem

### Eigenvalue Theorem (#1)
Let $A \in M_{n,n}(C)$ and $\lambda \in C$. Then $\lambda$ is an eigenvalue of $A$ if and only if
$det(A - \lambda I_n) = \vec0$

We define a characteristic polynomial of $A$ by $$P_A(\lambda) = det(A - \lambda I_n)$$ Therefore $\lambda \in C$ is an eigenvalue of $A$ if and only if it is a root of the characteristic polynomial of A.

A proposition states...
Let $A \in M_n(C)$ and $\lambda \in C$ be matrix and its eigenvalue. Assume $V_\lambda$ is the set of all eigenvectors of $A$ corresponding to $\lambda$ and zero vector in $C^n$. Then $V_\lambda$ is a subspace of $C^n$.
The set of all eigenvectors does not contain zero and that is the only problem, so we just 'add' it to then declare it a subspace

!! This is an important place to note that this only applies for square matrices, because otherwise they would send a vector to a different dimension. Only square matrices !!

In an answer to calculate the characteristic polynomial of $A$, it is sufficient to leave the lambdas in the answer, factorized. No need to compute the lambdas, just show the roots.


To compute the set of all eigenvectors, we have to find the kernel of the matrix.
This is because we are searching for all vectors satisfying $(A - \lambda I)x = \vec0$
Therefore $V_\lambda = ker(A - \lambda I)$

A Lemma states that for a square matrix $n \times n$, its characteristic polynomial is a polynomial of degree $n$.

A theorem states given $A \in M_n(C) \implies \sigma(A) \neq \vec0$ 
By fundamental theorem of algebra, since there is at least one root, sigma of $A$ is non-empty.