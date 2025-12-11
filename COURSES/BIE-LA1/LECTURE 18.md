## ...Continuing Spectral Theory

$spec(A)$ or $\sigma(A)$ denotes the spectrum of $A$. The spectrum is the set of eigenvalues.
An eigenvalue is in the spectrum of a matrix if and only if there exists a non-zero vector such that its product with the matrix is a scalar multiplication of itself by that eigenvalue.
$$\lambda \in \sigma(A) \iff \exists v \neq 0$$                                                                        such that
$$Av=\lambda v$$ Has a non-unique, non-zero solution, so it is not invertible, and so
$$det(A - \lambda I_n) = \vec0$$
Then, let us look at the polynomial of degree $n$ $P(\lambda)$ 
Where $n$ is the same as $M_{m,n}(C)$
$P(\lambda)=\alpha(\lambda - \lambda_1)^{l_1}...(\lambda - \lambda_n)^{l_n}$
When a root is repeated twice, its 'multiplicity' increments, and the exponent grows.
Then, given that the roots are different, the sum of the exponents (multiplicities) is equal to the degree.

If $\lambda_i$ is a root of $P(\lambda)$...
$P_A(\lambda_i) = det(A - \lambda_i I_n)$ 
Obtaining a polynomial of degree n is difficult, but there are methods to compute it easily. To obtain the spectrum of $A$, we must solve the polynomial characteristic.

We also see that:
if $v$ is an eigenvector then $\alpha \neq 0$ $\alpha v$ is also an eigenvector (corresponding to $\lambda_i$)
If $w$, $v$ are vectors in the spectrum, then $w+v$ is also in the spectrum

The eigenspace is the set of all eigenvectors associated to $\lambda_i$ - then union with the zero vector (which it originally lacks).
It is also finite dimension, so you can find a basis and dimension for $V_\lambda$ 
For every eigenvalue we will have a different eigenspace with its unique dimension and basis.

Let us consider the following.
$\lambda_i \in \sigma(A)$
$P(\lambda) = \alpha(\lambda - \lambda_1)^{l_1}...(\lambda - \lambda_n)^{l_n}$

Let the algebraic multiplicity of $\lambda_i$ be $l_i$
$\mu(\lambda_i)=l_i$
Where $\mu$ maps our root to its multiplicity.
Then the geometric multiplicity of $A$
$\mu_g(\lambda) := dim(\mu_i)$ 
And according to theorem, $\mu_g(\lambda_i) \leq \mu_\alpha (\lambda i)$

$v_{\lambda_i} = \{v: Av=\lambda_iV\}$ 
If the vector is zero, that is by definition.
If it is non-zero, it is an eigenvector corresponding to the current eigenvalue.

$=\{v ~|~ (A-\lambda_iI_n)v = \vec0\}$
Notice that this follows the same definition as the kernel.
=$ker(A-\lambda_i I_n)$
And we know how to get the basis of a kernel.

Let us now define...
Let $A, B \in M_n(C)$
We say that $A$ is **SIMILAR** to $B$ if exists an invertible matrix $P \in M-n(C)$ such that 
$$A = PBP^{-1}$$
Then we write $A \sim B$ 
This is an equivalent relation. It holds transitivity, symmetry, and reflectivity.
Some of their properties are similar to each other.
If two matrices are similar, they have the same spectrum.

First of all, we know that they have the same determinant, as by the definition of the determinant, we may write it as $det(A)=det(B)det(PP^{-1})=det(B)$ 

If two matrices are similar, they have the same characteristic polynomial.
Then, it follows that the spectrum of one matrix is equal to the spectrum of the other.
Additionally as consequence, if they have the same characteristic polynomial, they have an equivalent multiplicity.
As theorem, $V_g^A(\lambda) = v_g^B(\lambda)$

The concept of isomorphic subspaces lacks in this course so we cannot prove it yet.

If $A$ and $B$ are given, how do you decide if they are similar?
How would you find a $P$ that satisfies it?
It's easy to disprove their dissimilarity. It's enough to disprove one of these:
- $rank(A) = rank(B)$
- $P_A(\lambda) = P_B(\lambda)$
- $\sigma(A) = \sigma(B)$
- $V_g^A(\lambda) = v_g^B(\lambda)$

Two matrices don't necessarily have the same basis if they are similar.

Diagonal matrices have nice properties which allow us to find the spectrum and algebraic multiplicity of each eigenvalue, which would be equal to the geometric multiplicity of eigenvalue - simply look at how many times the eigenvalue repeats in diagonal.

If $A$ is similar to a diagonal matrix, we know they are sharing the multiplicities, spectrum and rank. If a complicated matrix is similar to a diagonal matrix, then you can read all the information about the spectrum of $A$ from the diagonal entries in $D$ (the matrix it is similar to).

The dimension of the kernel is the number of the free variables.

For TA: What is the difference between geometric multiplicity and algebraic multiplicity?


By definition, matrix  $A \in M_n(C)$ is called diagonizable if $A$ is similar to some diagonal matrix.
Then, it is easy to compute spectrum of $A$ and other information.

First question, how could we deduce that a matrix is diagonizable?
Second question, how do we then find the diagonal matrix and invertible matrix?
$\exists ~ S$ invertible and $D$ diagonal
such that $A=SDS^{-1}$

The rest of the lecture will be tackling this issue.

First, we find the basis of the vector space that our matrix belongs to, such that each vector in the basis is an eigenvector of the matrix.
That is, $Av_i = \lambda_i v_i$ for $v$ in $(v_1,...,v_n)$
$A$ is diagonizable if and only if the vector space admits a basis whose eigenvalues form a basis for the vector space the matrix belongs to.
We will be needing the entirety of linear algebra to tackle this.

She will put some of the proofs in the exam, for grade A you would need to know the proofs.
One of the proofs is this theorem.

...

According to theorem,
$A$ is diagonizable $\iff$ algebraic multiplicity of each eigenvalue is the same with the geometric multiplicity. That is $\mu_a(\lambda)=\mu_g(\lambda) \forall \lambda \in \sigma(A)$ 
Then we have left computing the similar diagonal.

Why diagonizable matrices are important, how to check for diagonazability, and how to compute the diagonal. This will be 30 points in the final exam.