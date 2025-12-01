
Continuing sorting and whatnot, we are now talking about the maximum subarray problem.
Given a sequence, the problem is to find a subsequence such that its sum in the subsequence is the greatest possible.
The brute force solution is to examine all pairs from the start and end indices in the array. Remember the pair resulting in the greatest sum. However, there are plenty of repetitions and unnecessary computations.

The brute force algorithm has time complexity T (n) ∈ O(n3).
The inner loop (k control variable) is not needed:
We know the sum of subsequence
a[i] + a[i+1] + ... + a[j]
If j increases by one, the sum could be easily updated by just
adding a[j+1] to the sum we already have from the previous
iteration.
This decreases time complexity to T (n) ∈ O(n2).

The solution can be done using just one loop (linear solution).
We set variable s (start of the subsequence) and proceed
towards the end of the array. As the elements are passed, the
sum is updated (and perhaps stored as the maximum).
If we get a negative sum, we know that the maximum
subarray does not cross the index. It either starts after that
index, or ends before that index. Thus, we may move the start
of the searched subsequence s after that index, set the sum to
zero and start another search.


### Problem Decomposition
Program design - problem decomposition.
Try to decompose the complex problem into simpler subproblems. 
You may use psuedocode, abstract commands, to solve subproblems. Use the abstract commands to create an outline of the solution, and use functions to implement abstract commands.

### Recursion
A programming concept where a function solving some problem solves itself to solve the problem. To use recursion, two conditions must be met.
The recursive call solves a smaller, simpler instance of the original problem.
Every recursion must have a basis case. It mustn't go "forever".
Function calls require stack space, which is reluctantly limited. Therefore loops are generally more widespread and used than recursion.
It is possible to implement a plethora of mathematical algorithms using recursion.
A few notable examples are factorial and GCD.

Recursive functions are usually short, straightforward, and easy to understand. Recursive functions tend to some inefficiency, as the problems may be recomputed many times. Many recursive algorithms may be replaced with iterative algorithms. Iterative algorithms usually work in a bottom-up way, from simple problem instances to more complex instances,