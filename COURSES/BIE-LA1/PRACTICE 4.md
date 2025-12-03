[[PRACTICE 5]]
## Invertible and Elementary Matrices

If we have a set A, and a set B, we can construct a mapping function between them.
$f: A \rightarrow B$
We can talk about the properties of the function. Injectivity, Surjectivity, Bijectivity
Injectivity: $\forall x ,y \in A : f(x) = f(y) \implies x = y$ 
Surjectivity: $\forall y \in B \exists x \in A:  f(x) = y$ 
Bijectivity: $\forall x ,y \in A : f(x) = f(y) \implies x = y$  $\land$ $\forall y \in B \exists x \in A:  f(x) = y$ 

Bijectivity is also called strictly one-to-one, as there is always a unique value.
Consider bijective functions.
$f: A \rightarrow B$
$g: B \rightarrow A$
They are inverses if and only of $g(f(x)) = x$ or $f(g(x))$. In formal words:
$g o f = id_A$ 
Where $id_A$ is an identity of the set. Everything that is plugged in, goes out.
$\pi \rightarrow \pi, 1 \rightarrow 1, 0 \rightarrow 0$  

If we have a matrix, we can say that they are functions. Matrix multiplication with a vector is the same as applying the function to a vector.
The rows of the multiplied should match the columns of the multiplier.
It's accepting something with the amount of rows as the amount of columns it has.

Side note reminder on matrix multiplication: 
$(AB)_{ij} = \sum A_{ij} B_{ij}$ 
Take your first row, multiply and sum by all the columns you can,
go a row down, until you are out of rows.
Matrix multiplication is not commutative.

As matrices are functions, we should have some identity function such that the input will be equal to the output. In general, it's a matrix n x n with 1's on the diagonal and 0's everywhere else.
Matrices are a function mapping vectors to vectors.

Let there be $f: R^3 -> R^2$ . This will be a matrix. It will take something in $R^3$ and output something in $R^2$. The matrix will have three columns and two rows. 
The matrix will look like: $M_{2,3}(F) \begin{bmatrix} a_1 && a_2 && a_3 \\ a_4 && a_5 && a_6 \end{bmatrix}$ 
And it will be given an input: $\begin{bmatrix} v_1 \\ v_2 \end{bmatrix}$ 
The number of columns corresponds to the dimension of the input, the number of rows corresponds to the dimension of the output.  When When a matrix goes from dimension m to dimension n, then it is denoted as $M_{n \times m}$ (?)

A mapping is linear if and only if:
$\forall x, y \in V : T(x+y) = T(x)+T(y)$
$\forall x \in V \forall c \in F : cT(x) = T(cx)$
Then, $M(v+u) = Mv + Mu$
Linearity means you can plug in constants and split addition.
Matrix multiplication is an applied function. You can distribute and pull out constants.
Matrix multiplication with a vector is always a linear mapping. Matrix multiplication with another matrix is composition of functions.
Therefore, matrix multiplication is not commutative. $f(g(x)) \neq g(f(x))$ generally.

Now that we understand that matrices are functions, we can talk about invertibility.
Given matrix A, when does there exists matrix B where $AB=I_n$? 
We won't prove this now, but matrices only have inverses when they're square.
It is not always invertible when they are square, but they have to be invertible. $n \times n$
The notation for square matrices is $M_n(F)$.
We call B a right inverse of A when we multiply it from the right. We call it a left inverse of A when we multiply it from the left. When it is the inverse, the right inverse and left inverse are equal. Then, if B is the inverse of A, $AB = BA$.
If there is an inverse matrix to a given matrix, then it is unique. 
Also, about inverse of two functions: $(f o g)^{-1} = g^{-1} o f^{-1}$ 
Therefore, the inverse of matrix multiplication: $(AB)^{-1} = B^{-1} A^{-1}$
Also, invertibility follows: $(A^{-1})^{-1} = A$

A detour into elementary matrices. When we do Gaussian Elimination, we take a matrix and apply operations on a matrix. The modern way of thinking of row operations, is applying matrix multiplication on the matrix. If we want to swap the rows of a matrix, we could write the row operations for swapping rows, but we can also look at it as the following: We can multiply it by some matrix that will swap the rows for me.
The matrix swapping rows will begin from the identity matrix, where the move the 1's such that the multiplication acts as a swapping. We move our row index down to the other one, and the other one up to the first one. The rest is zero, filling the gaps.
The matrix multiplication for multiplying a row by k, we can start from the identity matrix and then change the 1 on the row where we are doing the multiplication by k.
Then, the last one, operations of taking a multiple of some row and summing it with some other row, and putting it inside the other row. The way we look at this, is the rows, in general, for a matrix, give things out, and the columns accept things in. We again start with the identity matrix, and then change of the zeros according to the row we are adding to the multiple we are adding it by.

To find the inverse for an n by n matrix...
When we get an REF matrix, we have obtained it by multiplying it by our row operation matrices such that $A' = E_n E_{n-1}...E_2E_1A$ 
Note that elementary matrices, row operations, are always invertible as we can always 'undo' a row operation.
To find the inverse of A, we can invert both sides.
$(A')^{-1} = (E_n E_{n-1}...E_2E_1A)^{-1} \implies$ 
$A'^{-1} = A^{-1}E_1^{-1}...E_n^{-1}$
Then, isolate $A^{-1}$ = $A'^{-1}E_nE_{n-1}...E_2E_1$ 
If we can reduce $A$ to an elementary matrix, then it is invertible.
We do GEM on $[A | I_n]$  and as a reminder GEM is the application of matrix functions so it is derived form the previous lemma.

Side note: Computers don't do it this way as it is not efficient, there is another method for them because of rounding errors, but we will do it by hand.

We do GEM on $[A | I_n]$ until $A$ reaches the form of $I_n$ Then the RHS will be the inverse of our matrix. If we find a zero row or column we know that we cannot reach the identity matrix, and so we know it is not invertible.