[[COURSES/BIE-LA1/LECTURE 14|LECTURE 14]]
### A bit more on matrix invertibility...

A matrix can be viewed as a function $M_{m,n}: F^n \rightarrow F^M$
A function can be injective, meaning every element in the preimage goes to at most one element in the image.
A function can be surjective, meaning there exist elements to map to any element in the codomain.
When a function is both, it is a bijection.
When a function is bijective, we are guaranteed an inverse function. Meaning, if we have some $f: A \rightarrow B$, and $f$ is bijective, we have another mapping $f^{-1}: B \rightarrow A$ such that $f o f^{-1}$ is the identity.
By inverse, we mean we want for any matrix A we want to find some B such that $AB=I_n$
<small> Identity matrix is 1's in the diagonal and 0's everywhere else </small>

How do we know that a matrix is invertible?
We are skipping over a few facts, like how the inverse of a matrix is unique. In the exam we don't know to provide the proof, just the theorem that the inverse of a matrix is unique. If A is invertible, then we denote its inverse by $A^{-1}$.
Finding this inverse is straight-forward. We won't go over the entirety of it, but still.
Every GEM row operation can be represented as a matrix multiplication from the left.
If we may reach the identity matrix through row operations on A, it is invertible, and moreover, we will have found its inverse.
$I_n = E_n...E_1A$ denotes the row operations we used (E) on the matrix (A) to reach the identity matrix.  Since the inverse is unique, we can take the inverse of LHS and RHS.
$I_n^{-1} = I_n = A^{-1}E_1^{-1}...E_n^{-1}$
Then, we can simplify multiply by the row operations.
$A^-1 = E_n...E_1I$
In a more practical sense, given the augmented matrix $[A|I]$, we reduce A to the identity and the matrix on the right will become the inverse of A.
In general, you do not know when a matrix is invertible when you just look at it. It has to be square, but being square isn't enough.
A matrix is invertible if and only if it can be reduced to the identity.
There is another rule saying that the determinant has to be non-zero but we cannot use it for this exam.

In a test, we should verify if it is the correct inverse. We would multiply the original matrix by our result, and see if the product results in the identity matrix.
First row times the first column, etc.
![[Pasted image 20251121184319.png]]

Before inverting a matrix, we should say that a matrix is invertible if and only if it can be row reduced to the identity matrix. Now I apply row reduction to a matrix, and we would state that we are augmenting it with the identity. Saying by a theorem the RHS will come out to be the inverse of the matrix.

## Kernels and Images (elementary matrix subspaces)

Again, a matrix is a function.
We always want to know the zeros of a function, when a function is equal to zero.
We always want to know when a matrix is equal to zero.
When we ask when a matrix multiplication is equal to zero, we ask when that SLE is equal to zero.
We investigate it further and we see that a matrix has more comprehensive structure than two dimensional functions.
A matrix has linearity: $A(v_1+v_2) = Av_1 + Av_2$ and also $A(cv_1) = cAv_1$
Matrices are all linear.
When we know that $Av_1 = \vec0$
Is $v_1$ the only one that makes it zero? Or then, what is the set of vectors that result in a zero?
$Av_1 + Av_2 = 0+ 0 \implies A(v_1+v_2) =0$
This suggests vectors, that I multiply with A and result in zero, are closed under addition.
$A(cv_1) = 0 \implies cAv_1 = 0$
Then, we have closure under scalar multiplication.
Vectors that go to zero when multiplied by a matrix are a subspace.
$A:F^n \rightarrow F^m \implies A \in M_{m,n}(F)$
The subspace of vectors that result in zero will be in $F^n$, as it is the 'input'. 
This subspace is denoted by $ker(A)$, being the kernel of A, or null of A, is a subset and subspace of $F^n$.
What about the image of the matrix? Given the same matrix, we can also ask what the vectors it maps look like. If we have some $v \in F^m$ what it maps to. These vectors also form a subspace of the codomain.
As an easy proof suppose we have $w_1 + w_2 = Av_1 + Av_2 = A(v_1+v_2)$ and so it is closed under vector addition. Similarly, we can show it is closed under scalar multiplication.
The subspace lives in $F^m$ as it the 'output'. It is called the image of A, denoted $im(A)$, it is the subspace and subset of $F^m$.

<small> A matrix that has a zero row is called degenerate when it takes input from more dimensions than it can output. It 'flattens' them. </small>

If we have matrix $A$, then the transpose will be $A^T$. It is "flipped to its other face and turned". 90's degrees clockwise and mirrored. You switch the placement of the rows and columns. 
Then, the kernel of the transpose and the image of the transpose are also subspaces.

$A \in M_{m,n}(F)$
$im(A) = \{w \in F^m | \exists v \in F^n : Av=w\}$
$ker(A) = \{v \in F^n | Av=\vec0\}$

Sidenote about matrices as functions:
The number of columns corresponds to the dimension of vector it inputs, the number of rows corresponds to to the dimension of the vector it outputs.
###### kernel of $A$, image of $A$, kernel of $A^T$, image of $A^T$ are the elementary subspaces.

The image of a matrix, in general, is the span of its columns.
If in REF we have a pivot in every row, we can say that the image of our matrix is equal to the span of our columns. We can remove redundant vectors in this process.

A basis is defined for the image of a matrix. If the list of vectors which make up its columns is LI and spanning, then it is a basis for the image of the matrix.

To investigate the kernel, the set of all vectors that result in a zero when multiplied by the matrix, we do row reduction and then multiply by an arbitrary vector and we simplify with these equations. Rewrite everything as simply as we can, and then we take out the arbitrary scalars making up our arbitrary vector. Then, the kernel will be the span of that single vector we get after taking out the scalars.
At the end we get the same equations whether we do it from the start or product the arbitrary vector in the end. We get the same equations in the end, so the set and subspace will still be the same. Marzieh so does it this way.

A few theorems that come from this.
Let's define $rank(A) = dim(im(A))$
If we have a a matrix $A \in M_{m,n}(F)$ then it holds that 
$m = dim(ker(A)) + rank(A)$
Fundamental theorem of linear algebra.
The dimension of a kernel which only contains the zero vector is defined as zero!

A matrix is invertible if and only if the kernel is $\{\vec0\}$. In other words, the dim(ker(A)) = 0

The definition of dimension is as follows: given any vector space V, all bases have the same length. The dimension is the length of any basis. The zero vector space has dimension 0.