[[COURSES/BIE-LA1/LECTURE 20|LECTURE 20]]
The determinant captures how much the matrix distorts the space.
The topic of eigenvalues and eigenvectors asks the question... We have a vector before a matrix is applied, does there exist a non-zero vector that stays in the same direction after the matrix is applied?

To define the eigenvalues, denoted by lambda: $$Av = \lambda v$$ All $\lambda \in C$ that satisfy the above for $v \neq 0$. Moving sides and factoring, $$(A-\lambda I_n)v=0$$ All numbers that satisfy this are the eigenvalues of $A$, making up $\sigma(A)$, the spectrum of $A$
This only holds when $$det(A-\lambda I_n)=0$$ We evaluate the determinant using lambda as a parameter, and achieve the characteristic polynomial of the roots of lambda. The roots compose our eigenvalues.

The algebraic multiplicity comes from the multiplicity of the roots, the geometric multiplicity comes from the bending of space in the linear transformation of the matrix.

Each eigenvalue has its own eigenvectors.
We may find it by plugging the lambda back in and solving the SLE $(A-\lambda_i I_n) = \vec0$
This eigenspace of eigenvectors will be the kernel of that matrix.
Then the geometric multiplicity will be the dimension of the eigenspace, which happens to be the kernel. So, it will be equal to the number of free variables in the REF while computing kernel.
It is also a vector space if we add the zero vector.

The eigenbasis is the basis that composed of eigenvectors of $A$, that is a basis of the vector space we are coming from.
You need enough eigenvectors such that you can have $n$ distinct directions with them. That means, the subspaces should also be large enough to permit that. And we need to have distinct eigenvectors in those spaces, to form a list (basis).

Every matrix has a least one distinct eigenvector.

We do not do spectral theory on finite fields.

We should usually justify some claims about algebraic and geometric multiplicity. We should be comfortable with these topics and be able to write.


When we have an existence claim and we know it's true, we need to give an example (or universal theorem). If we know it's false, we need to universally disprove it with a theorem.
When we have a universal claim and we know it's true, we have to prove it with a theorem.
If we know it's false, we have to give a counterexample.

Fundamental Theorem of Linear Algebra $A \in M_{mn}(F)$  then $rank(A)+nullity(A)=n$
