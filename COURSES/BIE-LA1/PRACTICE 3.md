
[[COURSES/BIE-LA1/LECTURE 11|LECTURE 11]]
90 minutes. not a lot of questions, but a lot of sub-questions.
No true false questions.
Allowed to use every thing we used in class, except theorems such as the column pivots. Marzieh wants you to understand that a matrix gives you a series of linear equations. When you have a pivot in every row, you cannot just jump straight to the answer. You have to elaborate that it represents that the SLE implies this and that.
She will not ask you to define span or linear independent. However, she wants you to know their definition. Given a linear independence, you have to know that it means that there is only one solution to the linear combination of the zero vector. 

##### Question examples:
Consider a list of 4 vectors in $R^4$.
First, she would like you to describe the span of these vectors. 
Before we even answer... What do we even know about the span?
It is the set of all linear combinations of these vectors.

We want to make a matrix of these four vectors. It will be 4 by 4, and you will write your vectors in the columns.
Marzieh wants you to know that you are not just putting numbers in a box and solving. You are inducing a system of linear equations in this way, representing it in a matrix.
It is important to remember your field. In our specific case:
$span(v_1, v_2, v_3, v_4) = \{v \in R^4 : \exists c_1, c_2, c_3, c_4 \in R$ s.t. $c_1v_1 + c_2v_2 + c_3v_3 + c_4v_4\}$
We want to solve $c_1v_1 + c_2v_2 + c_3v_3 + c_4v_4 = d$
Where we have arbitrary scalars and an arbitrary result matrix. 
The next step is augmenting our matrix. Essentially, take the matrix of the vectors, and then add another column representing the result, and add a line between the coefficients and the $d_1, d_2, d_3, d_4$. 
Marzieh will take points off if you do not write the thought process from span to augmented matrix. Half the battle is setting this system up. 
Our goal is to find such vectors...

We say this explicitly: We will now apply **Gaussian Elimination** to the matrix. 
Don't just start doing things. You have to write what you're going to do, before you do it.
"We use Gaussian Elimination to simplify the SLE, to find the constraints of $d_1, d_2, d_3, d_4$"
You need to have the buzzwords in a way that makes sense.
We use this GE to algebraically simplify the SLE to better understand the span of the space. She won't give you a zero for saying "constraints" or other words she hasn't used.
The entire idea is that the matrix gives you a series of linear equations.

If you, for example, take a row and divide it by two, you have to label the operations in-between rewriting the matrices. We want to reach a "staircase" form, where every row has a pivot. As a reminder, a pivot is the first non-zero element. You can add rows you can multiply rows, you can do scalar multiplication of rows, swap rows, just have to label it.

It is recommended, as practice, to do GEM on your own before the exam with a timer to get faster at it, and as to not get stuck on the exam.
This goes without saying, there are many ways to do GE, and they are all correct. If you do everything correctly, you describe the same SLE.
As a side note, you are not required to reach RREF in the exam, only REF. RREF or some hybrid of it with REF will make it easier, of course, as it will zero out one of the other elements. but it is not necessary to know it for the exam.

As a word of advice. When you subtract rows, think of it as adding a negative multiple. This is especially useful when working in $Z_p$. 

A zero row in an augmented matrix implies a free variable.
After we arrive at REF, we transform it back to the SLE.
Matrix $A$, the matrix of all our vectors, times the vector $x$, a vector of all our scalars, is equal to the result, in our case, an arbitrary vector. Each row is an equation.
Marzieh will allow saying that every row without a pivot implies a free variable.
"Column [x] does not have a pivot that corresponds to scalar [x] being a free variable. Thus span can be described by $v_1, v_2, ... v_{[x]-1}$"

We are allowed to use that the theorem that an augmented matrix has a pivot in every row implies that the list is spanning. And the opposite: If a row has no pivot, hence the list of vectors is not spanning, by the lectures.

Next!
A list of vectors is linearly independent if and only if the only linear combination of these vectors that equals zero only when the scalars are trivial (all equal to zero).
X is LI if and only if $c_1v_1 + ... c_nv_n = 0 \implies c = 0 \forall c_1, c_2, c_3, c_4$   
You could redo the GEM, but it will end up completely the same, and the RHS will be entirely zeros.
When finding a free variable with that, you will find more than one solution. You will find coefficients whose linear combination is equal to zero but they themselves are not equal to zero. Therefore, the list of vectors is LD.
In the exam, we will need to provide an example of the list of scalars for which the linear combination is equal to zero vector but they are not all zero. In this case, we would want to use the free variable, setting it to whatever we want (the easiest is `1`), and evaluating the scalars (to show they are non-zero).

Next!
What is the dimension of the span of a list of vectors, that does not span a whole field? It spans its own span. If you drop the linearly dependent vectors, it becomes linearly independent, and then it spans and is LI, therefore it is a basis. The dimension of anything is the length of its basis. Therefore, we given a span, we must reduce it to be LI, and then take its length, and that will be the dimension.  The definition of dimension is the number of elements in a basis. Maximum length of LI, Minimum length of a span.
To drop the linearly dependent vector: remove the column with no pivot. Because there is no pivot we can write every entry here as a linear combination of other vector, so we have to drop one of them. Basically, drop the columns such that there are no "leveled" places in the "staircase". 

By theorem, If you have a list of vectors, and one vector in that list can be written as LC of other vector, removing that redundant vector will not change the span of that list.

Next!
For field V, a subspace is a subset of vectors of the vectors of V, and is closed by vector addition and scalar multiplication. This also implies that zero has to be inside. You don't have to state it, but it is necessary. Being a subspace implies the existence of zero.
For example, vector $\begin{bmatrix} a \\ b \\ c \end{bmatrix}$ in $R^3$ where c = 0 and a = b. It is a subspace because the zero-vector is in the subspace, it is closed under scalar multiplication and vector addition. You must show it for an arbitrary scalar and arbitrary vector, you cannot give just "any number" unless you are showing a counter-example. In which case, you need to find 2 vectors that satisfy the conditions of the subset, and try to do the operations on them ,and find a contradiction.

One important thing Marzieh said, you can see that $v+cu \in A$ in one step, but she prefers you to split vector addition and scalar multiplication into two conditions. 

In general, if it's a subpsace, it holds in a general space, if not, show it fails under a condition and show a counterexample.