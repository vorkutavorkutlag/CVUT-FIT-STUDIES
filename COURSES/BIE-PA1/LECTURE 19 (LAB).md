[[LECTURE 20]]

In many cases where we handle recursion, we have interlaps of computation. We should not have duplicate computations, as that results in inefficiency. We should store the computation results in advance and keep reusing them instead of recalculating them over and over.
That is called memorization/memoization, involving saving our computation results into a cache (for example, two dimensional array in a Fibonacci tree), and then accessing the cache when we would have otherwise recomputed.

Global variables and static variables are initialized to zero, whereas the initialization of local variables is undefined behavior.

