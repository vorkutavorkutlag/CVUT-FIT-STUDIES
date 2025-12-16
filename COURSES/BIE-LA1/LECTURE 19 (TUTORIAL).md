[[PRACTICE 8]]
## Eigenvalue, Eigenvector, Diagonalization

For a matrix $A \in M_n(C)$, decide if $A$ is diagonizable or not. If yes, find invertible matrix $S$ and diagonal matrix $D$ such that $A=SDS^{-1}$

$A$ is diagonizable if and only if $v_g(\lambda)=v_a(\lambda) \forall \lambda \in \sigma(A)$

If $C$ admits a basis of the eigenvectors of $A$ is also a theorem, but the theorem above is what we should use.

For the first step, we need to compute and factor $P(\lambda) \implies det(A-\lambda I_n) = 0 \implies \alpha(\lambda - \lambda_1)^{l1}...(\lambda - \lambda_m)^{lm}$ 
Will almost definitely need to use the expansion formula.
Such that the eigenvalues by indices are not equal to one another.
Then $\sigma(A) = \{\lambda_1,...,\lambda_m\}$ and $v_a(\lambda_i)=l_i$ (the multiplicity)

Second step. For each eigenvalue $\lambda_i$
We have the definition $\mu_g(\lambda_i)=dim(ker(A - \lambda_i I_n))$
Which is equal to $n - rank(A - \lambda_i I_n)$
/\* Which is equal to the number of pivot columns in REF of $A$ \*/
Which is equal to the number of free variables.

If YES, then for each eigenvalue $\lambda_i$ we need to find a basis of $V_{\lambda_i}$
Essentially we need to solve SLE $R_ix = \vec0$ and find a basis $B_{\lambda_i} = $

Third step. $detB := B_{\lambda_i}\cup...\cup B_{\lambda_m}$ Then B is a basis of $C^n$ of eigenvectors of $A$, so by proof of theorems we have $S=[I]_{\epsilon \leftarrow B'}$

D is a diagonal matrix with diagonal entries $\lambda_{11},...,\lambda_{1m}$, $\lambda_{21},...,\lambda_{2m}$ , $\lambda_{m1},...,\lambda_{mm}$
Repeated $\mu_a(\lambda)$ times.
For 0 with algebraic multiplicity 1, and 1 with algebraic multiplicity 2, we will get $$D=\begin{bmatrix}0 & 0 & 0 \\ 0  & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}$$
In the exam, she will say that the spectrum of $A$ for example should be $\{0,1\}$ 
This will ensure that we achieved the characteristic polynomial correctly.