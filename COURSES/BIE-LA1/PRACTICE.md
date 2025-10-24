### Vector Subspaces

Given a field V, and a subset S of V $(S \subset V)$, if:
1. $\forall x \in S \forall a \in F ax \in S$
2. $\forall x, y \in S x + y \in S$

Though, it is possible to combine them into one statement:
$\forall a \in F, \forall x,y \in S x + ay \in S$

To the question of to give examples of subspaces of $R^3$, saying that $R^2$ is a subspace is the wrong answer. That is because coordinates in $R^3$ have three components, whereas $R^2$ has only three components. Strictly, it is not a subspace. It is possible to rigorously prove, but it is not relevant to this course.
Some examples of subspaces of $R^3$ include $\{ \begin{bmatrix} 0 \\ 0 \\ 0\end{bmatrix} \}$, or $R^3$ itself. these two are trivial subspaces.
There cannot ever be an empty subspace. There must exist a zero, some additive identity, something, which an empty subspace lacks.

Subspaces of $R^2$, for example, include any function who's domain is in $R^2$ and pass through the zero of that field. For example, $y=x$ can be defined such as:
$S = \{\begin{bmatrix} a_1 \\ a_2 \end{bmatrix}\ \in R^2 : a_1 = a_2\}$

If we try the same thing with quadratic formulas, say $y=x^2$:
$S = \{\begin{bmatrix} a_1 \\ a_2 \end{bmatrix}\ \in R^2 : a_2 = {a_1}^2\}$
We try to test it with the definition of the subspace. 
$\begin{bmatrix} a \\ a^2 \end{bmatrix} + \begin{bmatrix} b \\ b^2 \end{bmatrix} = \begin{bmatrix} a+b \\ a^2+b^2 \end{bmatrix}$ 
However, $(a+b)^2 \neq a^2+b^2$ therefore it is not a subspace.
This also follows why we tackle linear subspaces exclusively.

Let's see an example with $R^3$ . If we separate it to 8 octants (quadrants, in three dimensions), and we want to create subspaces out of each octant.
$S = \{\begin{bmatrix} a_1 \\ a_2 \\ a_3 \end{bmatrix}\ \in R^2 : a_1, a_2, a_3 \geq 0\}$
This would be the first octant. It is closed for the two conditions. However, since it is only positive numbers, if we multiply by a negative scalar, we see that the result is not in S.
Let $c \in R^-$ 
$c * \begin{bmatrix} a_1 \\ a_2 \\ a_3 \end{bmatrix} = \begin{bmatrix} c*a_1 \\ c*a_2 \\ c*a_3 \end{bmatrix}$ where $c*a_1, c*a_2, c_a3 \neq 0$, which is not in our domain.

Now, let us try to understand this topic through pure computation rather than visualisation, so that we will be able to tackle more complex problems.
Consider vector space V.
What is the smallest subspace that contains an arbitrary non-zero vector?
In $R^2$ , it is a line passing through zero and the required vector. If we were checking for passing through the zero vector, then {[0, 0]} would have been a sufficient subspace. Now, this applies for every field, the smallest subspace that contains and arbitrary non-zero vector is in that span.

The span of a set of vectors is a subspace of the field V. 
For every given subspace of V, it must also contain the span subspace.
That is because it contains both scalar multiplication $c_n * v_n$ and $c_n *v_n + c_{n+1} * v_{n+1}$. 
For example, the span of $\begin{bmatrix} 1 \\ 0 \end{bmatrix}$ and $\begin{bmatrix} 0 \\ 1 \end{bmatrix}$ is $R^2$ 
Outside of being viewed as a math problem, it can also be interpreted as freedom of movement. Being able to move across the entire infinite line, and the other infinite line(s), where we are able to get? If the infinite lines are not exactly the same (not $180^o$), then it can represent any other point in that domain, there are no constraints.


Let us consider the modulus fields.
$Z_3^2 = \{\begin{bmatrix} a_1 \\ a_2 \end{bmatrix} : a_1, a_2 \in z_3\}$
We have the subspace:
$\{\begin{bmatrix} a_1 \\ a_2 \end{bmatrix} \in Z_2^3: a_1 = 0\}$

Next we will be discussing Linear Independence and Gauss Elimination

First, consider the list of vectors
$\{v_1, ..., v_n\}$
To see whether this list is linearly independent, for all:
$c_1v_1 + ... + c_nv_n$ = 0
necessary implies $c_1 = ... = c_2 = 0$
This property tells us that if a list of vectors is linearly independent, then you can uniquely represent any vector in the span of these vectors using those vectors. It only has one solution, as you cannot swap one vector for another.
Secondly, returning to the freedom of movement, it means that every vector adds a possible direction to this realm on which we can span.
Naturally, we want to ask when a list of vectors is linearly independent.
The answer to that is solving the series of linear equations (SLE) for every $c_n$ and to see if they are all equal to $0$.

You look for non-zero solutions by solving the augmented matrix in the Gauss Elimination. If there are any non-zero solutions, than they are not linearly independent. If there are multiple solutions, then you don't have linear independence. It has to have a unique solution for linear independence.

To find if the vector set { $\begin{bmatrix} 5 \\ -2 \\ 1 \end{bmatrix}$, $\begin{bmatrix} 2 \\ 0 \\ 3 \end{bmatrix}$ , $\begin{bmatrix} 7 \\ 0 \\ 4 \end{bmatrix}$ } is linearly independent, we first make an augmented matrix.

$\begin{bmatrix} 5 && 2 && 7 && | 0 \\ -2 && 0 && 0 && | 0 \\ 1 && 3 && 4 && | 0 \end{bmatrix}$   
Using Gauss Elimination method with Row Operations, we may finally get the result:
$\begin{bmatrix} 1 && 0 && 0 && | 0 \\ 0 && 6 && 21 && | 0 \\ 0 && 0 && -13 && | 0 \end{bmatrix}$   
Each row has a pivot, and it follows a 'staircase' form. That means there is only one unique solution to the question.
Gauss elimination let's us know if there are more than one solutions (causes the lack of linear independence, i.e. linear dependence).

There is a very, very useful slide to use for everything we went over in this lecture.
Christianbhughes.com
https://christianbhughes.com/subspacesAndSpan.pdf