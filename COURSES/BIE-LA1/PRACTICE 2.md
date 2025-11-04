Last time we talked about span and linear independence.

Vectors are linearly dependent if they are related by a scalar.

Consider again $R^2$.
The list consisting only of $\begin{bmatrix}1 \\ -1\end{bmatrix}$ is linearly independent.
If we add vector $\begin{bmatrix}1 \\ 1\end{bmatrix}$, the list consisting of both of them we have a linearly independent list, and spans $R^2$. If we add a third vector, it is in some sense redundant, as we can represent it with the two vectors.
This is an example of the proposition which applies to $F^n$. 
Consider $F^n$ . If the list $(v_1, ..., v_m)$ is $LI$, then $m \leq n$.
We have a similar constraint on span. Intuitively, the span is telling us what we can reach with a combination of our vectors. 
Consider $F^n$ . If the span $span(v_1, ..., v_m)$ spans $F^n$, then $m \geq n$.

In a reduced row echelon form, you have to make sure all the pivots are equal to `1`, and that the columns above the pivots are zeros. This course will not require knowing how to achieve it.

In an exam, we want to write that the REF gives us the following equations, and if there are any redundant columns, i.e., no pivots and equal to zero. As a consequence, we may find a free variable. If you just write that it does not having any pivots implies you are in the span of the previous vectors.


Given the two propositions from before, about the $LI$ and $span$ ranges, there is a special event in their intersection. When there is a vector list that spans across a field, and the list is also $LI$, then it is called a **Basis**. When both inequalities intersect where $m=n$, it results in a linearly independent list that spans across the field - it is barely spanning and barely linearly independent.

If and only if a vector list in $F^n$ is linearly independent, then it also spans $F^n$.

###### Definition
Let $V$ be a vector space.
Then $(v_1,...,v_n)$ is a basis if and only if it spans and is $LI$.
It is called a basis since you can build your entire field from it.
A basis needs the number of vectors the size of the field's exponent.
$(v_1,...,v_m)$ is a basis only when $m = n$.
