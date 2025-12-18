[[COURSES/BIE-LA1/LECTURE 21 (TUTORIAL)|LECTURE 21 (TUTORIAL)]]
### ...Continuing similar matrices

Given two matrices $A, B$ in the same vector space, they are similar if there exists an invertible matrix $S$ such that $A=SBS^{-1}$
Then, we write $A \sim B$ 

Then, we also know that their characteristic polynomials equivalent, that being
$P_A(\lambda)=P_B(\lambda)$
From here it also follows that their spectrums are the same, that being
$\sigma(A)=\sigma(B)$
Then it also follows that their algebraic $(\mu_{a_A}(\lambda), (\mu_{a_B}(\lambda)))$ and  geometric $(\mu_{g_A}(\lambda), (\mu_{g_B}(\lambda)))$ multiplicities are respectively equivalent to one another.
We know that their ranks are equivalent, and that their determinants are equivalent.

$A$ is diagonizable $\iff$ it is similar to a diagonal matrix.

The procedure to follow when given two matrices to see if they are similar.
Similar matrices have to adhere to **all** of these properties.
- Check if $P_A(\lambda) = P_B(\lambda)$ 
For that, we compute the determinants of $(A-\lambda I_n)$ and $(B - I_n)$ and equate them to 0.
- ...The rest?

You may show that the characteristic polynomial of a matrix is equal to the characteristic polynomial of its transpose using the attributes:
$(A+B)^T=A^T+B^T$ and additionally $det(C^T)=det(C)$
also $(CD)^T=D^TC^T$
Then, also use the definition that the characteristic polynomial $P_A(\lambda)=det(A-\lambda I_n)$ 
And likewise, $det(A-\lambda I_n)=det((A-\lambda I_n)^T) = det(A^T-\lambda I_n^T) = det(A^T - \lambda I_n) = P_B(\lambda)$ 

Note that the inverse of the transpose is equivalent to the transpose of the inverse.
$(S^{-1})^T = (S^T)^{-1}$ 
We can show this by showing that $(S^{-1})^T$ is the inverse of $S^T$ by multiplying and pulling out the transpose. Then we get that it is equal to the transpose of the identity, being the identity. Since we only have one unique inverse, we show $(S^{-1})^T = (S^T)^{-1}$ 

Then, from these properties we see that if $A$ is diagonizable, then its transpose is also.

We should show the entire train of though proofs, how we obtained these equalities in each step.

In the exam we can use the fact $A$ is diagonizable $\iff A^T$ is diagonizable.

Show that if $A$ is not invertible, then $0 \in \sigma(A)$
To show that, we have to show that $0$ is a root. That is, $P_A(0) = 0$
We see that $det(A) = 0$ Then $P_A(0)=det(A-0*I_n)=det(A)=0 \implies$ 0 is a root
$\implies 0 \in \sigma(A)$ 
We may use the converse of this as well by going 'backwards'.

The sum of the algebraic multiplicities is the degree of the polynomial, being the dimension - $n$. 
Recall also $1 \leq \mu_g(\lambda) \leq \mu_a(\lambda)$

The diagonal of a diagonizable matrix is the identity, composed of the roots of the spectrum, repeating as many times as is their algebraic multiplicity.