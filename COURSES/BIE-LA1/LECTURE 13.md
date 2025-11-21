[[LECTURE 13 - PART 2]]
## Change of Bases

A finite dimensional vector space have more than one basis. Let B and A be two bases for a vector space V. Then for any vector $v \in V$, one can compute two column vectors $v_A, v_B$ we aim to understand how these two column vectors are related to each other.

Let A, B, be two bases for the vector space V over field F. The change of basis matrix from A to B is denoted by $[I]_{B\leftarrow A} \in M_{n}(F)$ is a $n x n$ matrix whose columns are ${a_1}_B...{a_n}_B$.

For the standard basis, the coordinates of any vector with respect to that basis is simply itself. 
For an arbitrary matrix, $B = (v_1, v_2, v_3)$
We need to find the solution of SLE where $c_1v_1+c_2v_2+c_3v_3=u$
Then, the coordinates will be the coefficients we solved.

Every vector can be written uniquely as a linear combination of the vectors in the basis. Therefore, a linear combination of two vectors with respect to some basis, the result will be also with respect to the basis. It can be proved by induction.

Let $A = (\begin{bmatrix} 1 \\ 2 \end{bmatrix}, \begin{bmatrix} 2 \\ 1 \end{bmatrix})$ and $\epsilon$ be the standard basis of $R^2$. Then
$[\begin{bmatrix} 2 \\ 1 \end{bmatrix}]_{\epsilon} = \begin{bmatrix} 2 \\ 1 \end{bmatrix}$
$[\begin{bmatrix} 1 \\ 2 \end{bmatrix}]_{\epsilon} = \begin{bmatrix} 1 \\ 2 \end{bmatrix}$
Thus,
$[I]_{\epsilon \leftarrow A} = A$
It holds generally.

__Theorem__
Suppose that A and B are two basis for the vector space V over field F. Then:
1. $[v]_B = [I]_{B \leftarrow A}[v]_A \forall v \in V$
2. $[I]_{B \leftarrow A}$ is an invertible matrix with inverse $[I]_{A \leftarrow B}$
moreover, it is a unique matrix satisfying item (i).

It is not necessary to know the proof for the test/exam, but, important to understand.
Let V be a vector space over F.
Let Basis $A = (a_1, a_2, a_3)$
Let Basis $B = (b_1,b_2,b_3)$
for $v \in V$
Thus $[v]_A = \begin{bmatrix} c_1 \\ c_2 \\ c_3 \end{bmatrix} \iff  v = c_1a_1 + c_2a_2 + c_3a_3$  by definition
$[I]_{B \leftarrow A} [v]_A = [I]_{B \leftarrow A} \begin{bmatrix} c_1 \\ c_2 \\ c_3 \end{bmatrix} = c_1[a_1]_B + c_2[a_2]_B + c_3[a_3]_B = [c_1a_1+c_2a_2+c_3a_3]_B = [v]_B$
We just use definitions of the coordinate of the vector, matrix vector multiplication can be written as linear combination of the columns. Then we can say that ith column of $[I]_{B \leftarrow A} = [a_i]_B$ and so our proof is complete.


Now, about the inverse.
$[I]_{B \leftarrow A} = [I]_{A \leftarrow B} ^{-1}$

$[I]_{\epsilon \leftarrow B} = [[b_1]_{\epsilon} [b_2]_{\epsilon} [b_3]_{\epsilon}] = [b_1 b_2 b_3] = B$ 
This one is easy, so we can then also easily calculate $[I]_{B \leftarrow \epsilon}$ by calculating inverse.

Second way to compute the coordinate of vector $v \in F^n$ with respect to basis B
We know by the theorem that $[v]_B = [I]_{B \leftarrow \epsilon} [v]_{\epsilon} = [I]_{\epsilon \leftarrow B}^{-1} v$

__Theorem__
Let V be a finite dimensional dimensional vector space over field F. Suppose that A,B,Y are bases for V, then: $$[I]_{B \leftarrow A} = [I]_{B \leftarrow Y} [I]_{Y \leftarrow A}$$

In the test, she will not ask us to inverse a matrix directly. She will give us two bases for a vector space and she will ask us to compute the change-of-basis $[I]_{B \leftarrow A}$
