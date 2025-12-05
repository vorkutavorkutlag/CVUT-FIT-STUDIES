
# Computing Determinants

The sigma in $S_n$ denotes a permutation. We can express a permutation as swapping two elements. After long enough, we reach the permutation.
The sign of a permutation is the number of a transpositions.
If we transpose a permutation, if we take two consecutive elements and change the order, then that is a transposition.
Then, $sgn(\sigma) = (-1)^{|S_n|}$ where $|S_n|$ is the number of permutations, equal to $n!$

To clarify, we are explaining $$det(A) = \sum_{\sigma \in S_n} sgn(\sigma) \prod_{i=1}^n A_{i, \sigma(i)}$$
Marzieh may ask to define this formula, but, you shouldn't use it... Too complicated.

Okay time for the actual topic.
We can stop looking at the determinant as a function of a matrix, and try to to look at it as a function of a sequence of vectors. However, what happens when we do a transposition to the sequence of vectors? Not to be confused with the transpose. Transposition is permutation. We would swap the places, and it would equal negative one times the original determinant.
$$det(v_1...v_{k+1},v_k,...v_n) = -1  * det(v_1,...,v_k,v_{k+1},...,v_n)$$ According to the definition of the determinant.
Basically, we can swap the columns, as long as we multiply by -1.

The determinant is linear, we can take out the scalar from the slot.
$det(v_1,...,cv_k,...v_n)= c * det(v_1,...,v_k,...,v_n)$
Likewise, we can pull out the sum.
$det(v_1,...,v_k+w,...,v_n) = det(v_1,...,v_k,...,v_n) + det(v_1,...,w,...,v_n)$

The determinant is a unique multilinear function in each slot and column on $n$ vectors that does these things.

If some vector is in the span of the others in a determinant, then the determinant is equal to zero. If the columns of our matrix is LI, then our matrix is invertible. 
Thus, matrix is invertible $\iff$ its determinant is zero.
A matrix whose determinant is zero is called singular.

The idea is you are compressing space into an information black hole when the determinant is zero. Again, the determinant represents by how much the determinant impacts the space. 

$det(A)=det(A^T)$ 
Also, we may apply GEM on rows AND columns when computing determinant.

Also, $rank(A)=rank(A^T)$

I'm very tired I am just writing what I hear at this point.
The determinant of a product is the product of the determinant.
$det(AB) = det(A)det(B)$
Additionally, $det(A^{-1})=det(A)^{-1}$


Row reduction is multiplication from the left, column reduction is multiplication form the right.