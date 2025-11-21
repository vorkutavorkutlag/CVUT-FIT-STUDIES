[[LECTURE 13]]
When checking whether two spans are equal to one another, it is also possible to see if the dimension of the first span is equal to the dimension of the second span which is equal to the dimension of the span of both of the vector lists.
$span(X) = span(Y) \iff dim(span(X)) = dim(span(Y)) = dim(span(X,Y))$
You may think you need three REF's to compute it, but it is also possible to compute at the same time $[X|Y]$. Once we obtain REF of one of them, we can compute dimspan of it, then the dimspan of the both $(X,Y)$ as a result, and then calculate the other REF separately.

Every LI list can be extended to a basis and every spanning list can be reduced into a basis.
$\epsilon = (e_1,..., e_n)$ is the standard basis of $F^n$, so we need to find which $e_j$ can be added to a list of vectors to make it LI and so a basis.
$[v_1, v_2 | e_1 e_2 e_3]$ 
We use GEM to reach REF. Then we see which vector we need to add corresponding to what pivot is 'missing'.