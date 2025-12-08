[[LECTURE 22]]
# ...Continuing Sorting

### Merge Sort

Efficient merging consists of reading the first elements of both sequences a and b, add the smaller of them to c and skip it in the corresponding source sequence. Finally add the remainder of `a` (`b`) to `c` (when the second sequence is empty.

```c
void merge(int *a, int na, int *b, int nb, int *c) {
	int ia = 0, ib = 0, ic = 0;
	while (ia<na && ib<nb)
		if (a[ia]<b[ib])
			c[ic++]=a[ia++]
		else
			c[ic++] = b[ib++];
	while (ia<na) c[ic++] = a[ia++];
	while (ib<nb) c[ic++] = b[ib++]
}
```

Simple sorting algorithms have time complexity $T(n) \in O(n^2)$ whereas efficient ones such as this one have a time complexity $T(n) \in O(nlogn)$ 
The merge sorting algorithm is based on the merge operation. The algorithm is stated recursively as the following:
- Array of size one element is sorted
- If the array has more than one element, split it into two arrays, each of one element
- Use merge sort to recursively sort the halves
- Merge the halves into a singular array
It is reminiscent of zipping up two arrays.


There is also an iterative approach to the merge sort.
The recursive merge sort function calls itself until the length of the sorted array is 1 element. At this point, the short split sequences are merged into longer sequences. The sequences are merged into a temporary array, the temporary array must be copied back to the source array.
However, iterative merge sort operates in a bottom up manner.
- Array `a` is split into sequences of length 1, the sequences are merged into an array `tmp` (sequences of 2 sorted elements)
- In the next iteration, the sequences (of length 2) from `tmp` are merged into sequences in `a` (sequences of length 4)
- again, in the next iteration, the sequences (of length 4) from `a` are merged into sequences in `tmp` (sequences of 8 sorted elements)
This continues until the array is sorted.
If the number of operations is odd, the result is stored in `tmp`, in which case it is necessary to copy the memory from `tmp` to `a`

![[Pasted image 20251208154240.png]]

Below is the complete bottom-up algorithm.
```c
void mergeSort ( int *a, int n) {
	int *tmp = (int*)malloc(n*sizeof(*tmp)),
		*src = a, *dst = tmp, *x;
	int len = 1, last = n-1;
	while ( len < n ) {
		int l = 0, r = len;
		while (l <= last ) {
			merge ( src, dst, l, min(r, n), min(r+len-1, last ) );
			l += 2*len;
			r += 2*len;
		}
		len *= 2;
		x = src; src = dst; dst = x;
	}
	if (src != a)
		for (int i=0; i<n; i++) a[i] = tmp[i];
	free ( tmp );
}
```

The only disadvantage of the algorithm is the need of the temporary memory space.
Other sorting algorithms, e.g. quick sort, overcome this limitation.


### Quicksort
Merge sort algorithm has time complexity $O(nlogn)$. This is asymptotically optimal, however, there are two disadvantage.
The hidden multiplicative constant is not small, and the algorithm needs an extra array to perform the sorting.

Be aware that there is a change for quicksorting to be somewhat slow. The worst case time complexity is $O(n^2)$ when the input data is tailored (rare case).
Though, empirically, its time complexity is $O(nlogn)$

Choose a pivot. Ideally, the pivot is the median value. The algorithm splits the array into two approximately halves. The lower half contains elements smaller than the pivot, the upper half contains elements greater than the pivot. Both halves are sorted recursively using this method. 
The choice of the pivot is crucial. If the choice is good, the halves are equally sized and the algorithm is fast.
In the case of a poor choice, the size is only decreased by one element and the algorithm degenerates into quadratic time complexity.

Finding the median is a difficult task. The average may be not obtainable, and we can't simply look in the middle... Consider this idea of almost-median pivot.
Good implementations use an approximation being random sampling, median of three, etc.

The pivot cannot move.

We have two indices on the two ends of the array. We iterate over in opposite directions, and whenever we find two values that are not "where they are supposed to be", we swap them.
After we find the 'middle', we 'draw a line' between the two halves and we can proceed.

One trick is swapping out our algorithm for another whenever we get down to arrays of a smaller size. Quick sort is able to sort smaller arrays, but then the multiplicative constant of the algorithm would be too big compared to its yield obtained by being able to work in a more efficient asymptotic way.
Some form of an 'endgame' algorithm.

To find a pivot...
We pick three random positions across the array. The middle one of those will be our pivot.

One way to fight a tailored input is to randomize/scramble it when it comes to you.

Library quick sort function...
Standard C library has an implementation of the quicksort algorithm. The implementation is available via the `stdlib.h` library.
The implementation is generic - it allows arrays of any elements to be sorted. The qsort function is a complete implementation of the quicksort function except the comparison itself.
The elements in the array must be compared and exchanged. The exchanging may be done in a byte-by-byte manner.
The comparison varies depending on the array content and sort criteria.
The programmer must supply a function to compare any two elements in the array, the function is passed as a pointer-to-function.
The comparison function is given pointers to two array values to compare. The return value is positive, zero, or negative for greater than, equal, or less than, respectively.

You can bet that sorting will be in the exam. Almost with eyes closed you should close them with qsort. Do NOT implement the sorting algorithm yourself

Modern CPU's don't execute an instruction in every cycle. Each instruction will take some number of CPU cycles, and its execution will be spread over, overlapping with some others instructions. For that case, the following comparison function is flawed.

```c
int intCompare(const void *a, const void *b) {
	const int * aa, *bb;
	aa = (const int *) a;
	bb = (const int *) b;
	
	if (*aaa < *bb) return -1;
	if (*bb < *aa) return 1;
	return 0;
}
```
These conditions, these branches, complicate the program for the CPU. The CPU can try to guess what's going to happen next, but the guess can be wrong.

The more efficient comparison function would be...
```c
int intCompare(const void *a, const void *b) {
	const int * aa, *bb;
	aa = (const int *) a;
	bb = (const int *) b;
	
	return *aa - *bb;
}
```

Or, even shorter,

```c
int IntCompare(const int *a, const int *b) {
	return *a-*b;
}
...

qsort((void*)arr, n, sizeof(arr[0]), (int(*)(const void *, const void *))IntCompare )
```

Note that we are casting the function.
Casting usually is dangerous, as it can change not only the representation but also the size.
The typecast in this case is convincing the compiler that we know what we are doing.
It works in this case, because the type-cast is well-thought. This won't always be the case.

Usually you want to trust the compiler to do these forms of optimizations, but in places like these where the optimizations are very simple, or in other case, very hard (such that the compiler cannot simply resolve it), it is better to do it yourself. Helping the compiler is always good. It is not a competition, rather a team game.

Note that we are casting from const void to const int because the type gets lost along the way, and because qsort accepts only the generic void type. Seeing as everything degrades into a void pointer, we may do some 'magic' with it.

Though, this solution may be problematic when talking about edge cases like INT_MIN and INT_MAX. Therefore, it could lead to some strange behavior due to underflow and overflow.

The absolute best way to implement it, is the following.
```c
return (*b < *a) - (*a < *b);
```
This is binary arithmetic. Let's look at all the cases.
- b smaller than a = 1 - 0 $\implies$ 1 $\implies$ a is bigger.
- b is equal to a = 0 - 0 $\implies$ 0 $\implies$ equivalent.
- b is greater than a =  0 - 1 $\implies$ -1 $\implies$ b is bigger.
This builds on the fact that boolean is compatible with integers.
True evaluates to one, and False evaluates to zero.

There is a way to make these more complex. Say, if we want to sort a structure of students first by the average, then by the surname, then by the first name
```c
int studentCompare ( const TSTUDENT *a, const TSTUDENT *b ) {
	int res = (b->avg < a->avg) - (a->avg < b->avg);
	if (res)
		return res;
	if (( res = strncmp ( a->surname, b->surname, NAME_MAX )))
		return res;
	return strncmp ( a->name, b->name, NAME_MAX );
}
```

In C++, there will be an easier way to write this.


### Linked Structures - List
The problem is the program reads integers from the input until EOF. The input then is displayed in reverse order.
The solutions include recursion, storing it in an array
...or storing in a linked list.
A structure is dynamically allocate for every input number.
The structure contains the value and a link to a structure holding the previous number in the sequence.
The structure containing the first number will have an empty link, `nullptr`
Linked lists are always read with a temporary variable.
There is a need to free the memory when using the linked list.

The proper way to free a linked list is as follows.
```c
while (st) {
	p = st->next;
	free(st);
	st = p;
}
```

If you are paranoid, you may set freed pointers to `nullptr` to avoid exploitation.