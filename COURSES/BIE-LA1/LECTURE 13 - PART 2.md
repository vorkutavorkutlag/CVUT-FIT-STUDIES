
Test 2. is on the first week of December on a Thursday
14:30-16:00
16:15-18:00
Must register on KOS.

"Not give up" -Marzieh

"When I write, I don't see sometimes" - Marzieh

If you wrote exactly what she wrote in the samples, you would have gotten maximum points
(of course, not including her mistakes)
## Determinant

In this lecture, we introduce one of the most important properties of a matrix: its determinant. Roughly, one can say that a determinant of a matrix is a measure of how "large" a matrix is.
To explain this we recall that every square matrix $A \in M_n$ can be thought of as a linear transformation that sends $x \in R^n$ to $Ax \in R^n$.
Thus matrix A sends the unit square (cube, tesseract, etc.) with sides $e_1, ...,e_n$ to the parallelogram (or parallelpiped, or hyper parallelepiped, etc.) with side vectors equal to the columns of A: $Ae_1,...,Ae_n$$

The determinant of A, denoted by det(A) is the area (or volume or hyper-volume, etc.) of this distortion of the unit square, in other words, it means how much A expands space when acting as a linear transformation.

Determinant of a matrix is the ratio of area of output region divided by area of input region.
It is not yet clear how to actually compute the determinant.
There are several different formulas for computing it, and they are all somewhat ugly and complicated.
Our strategy is to start by looking at some of the basic properties of determinant instead.

if A is the identity matrix, then the determinant of A is 1. 
$$det(I_n) = 1$$
Since every matrix expands by a factor of det(A) and similarly each B expands by a factor of det(B), it must be the case that AB stretches space by the product of these two factors.
$$det(AB) = det(A)det(B)$$
If we multiply the columns of A by a scalar $\lambda \in R$  then geometrically this corresponds to multiplying one of the sides of the output parallelogram by $\lambda$, which in turn scales the area of that parallelogram by $\lambda$
$det(A_1...\lambda A_i...A_n) = \lambda det(A_1...A_i...A_n)$

Likewise, if we add a vector to one of the columns of the matrix:
$det(A_1 + v | A_2) = det(A_1 | A_2) + det(v | A_2)$


The definition of the determinant is the unique function/mapping det : $M_n(F) \rightarrow F$
which satisfies the following properties:
1. Normalization: $det(I_n) = 1$
2. Product property: $det(AB)=det(A)(det(B) \forall A, B \in M_n(F)$
3. Linearity in each column: For any vectors $A_1,...,A_n, v \in F^n$ and $\lambda \in F$ we have:
$$det(A_1...\lambda A_i+v...A_n) = \lambda det(A_1...A_i...A_n) + det(A_1...v...A_n)$$

##### The determinant of an invertible matrix
Let A be an invertible matrix in $M_n(F)$ such that $AA^{-1}=I_n$
Then, by product property and normalization property, we get:
$$1 = det(I_n) = det(AA^{-1})=det(A^{-1})det(A)\implies det(A^{-1})=det(A)^{-1}$$
As a remark, if and only if A is invertible then $det(A) \neq 0$


__Lemma__
if a square matrix has a zero column then $det(A)=0$

__Corollary__
The determinant of zero square matrix is zero.

__Theorem__
if and only if A is not invertible then $det(A) = 0$


#### Computing
If A is not invertible the determinant is zero.
If A is invertible, the determinant is non-zero. How do we compute determinant?
Then RREF of A is $I_n$ by row operations from right to left.
We apply $RO_1, RO_2, RO_3, ..., RO_m$
$A \rightarrow A_1 \rightarrow A_2 \rightarrow A _3 \rightarrow ... \rightarrow I_n$
Each row operation is an elementary matrix that is the identity matrix after we applied the row operations. Row operation can be expressed as matrix multiplication $E_nA_n = A_{n-1}$
Then $I_n=E_m...E_1A$
Each elementary matrix is invertible, so their determinants are non-zero. 
Then $det(I_n)=det(E_m...E_1A) = det(E_m)...det(E_1)det(A)$
$\implies det(A) = det(E_1)^{-1}...det(E_m)^{-1}$
We can obtain the determinants of those elementary matrices just by using the properties and definition of the determinants. For every row operation:
Scalar multiplication: c
Addition: always 1
Swapping: always -1  

__Theorems__
Let E be an elementary matrix obtained by the addition row operation $R_j+cR_1\rightarrow R_j$ on the identity matrix. Then $det(E)=1$
Let E be an elementary matrix obtained by the multiplication row operation $cR_i \rightarrow R_i$
on the identity matrix. Then $det(E) = c$
Let E be an elementary matrix obtained by the swap row operation $R_i\leftrightarrow R_j$ on the identity matrix. Then $det(E)=-1$

Let A be invertible, suppose that A can be row-reduced to identity via $k$ multiplication row operations as well as $s$ swap row operations (we do not care about addition operations). Then, $det(A)=(-1)^s(c_1...c_k)^{-1}$
