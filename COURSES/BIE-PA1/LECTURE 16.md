
## Pointer Continuation and Dynamic Memory Allocation

So far, we have been using memory which was ours from the beginning of the memory. We had variables, but we could not create variables with an arbitrary size. For that, we have to get familiarized with this topic.

### Pointer Arithmetic
Pointers may participate in addition, subtraction, and comparison. The following gives an overview of allowed operations:
```
T* + int -> T*
T* - int -> T*
T * - T* -> int
T* rel op T* -> int
```
If an integer `n` is added to a pointer `T*`, the resulting address is the base address increased by `n * sizeof (T)` bytes. The same applies for subtraction. If two pointers are subtracted, the resulting integer is the number of elements T between the two pointers.
The result of pointer comparison is based on the actual addresses (greater than, less than, equal to the address).

C has a special treatment of statically allocated arrays. A statically allocated C array can only evaluate its size using the sizeof operator, and implicitly convert itself to a constant pointer to the array zeroth element.
An array in C is for all intents and purposes a pointer.
If a is an array (or pointer) and i is an integer, the following
holds: `a[i] = *(a+i) = *(i+a) = i[a]`

```c
/* "array" version */
void readVector1 ( int v[], int n ) {
	printf ( "Enter %d numbers:\n", n );
	for ( int i = 0; i < n; i ++ )
		scanf ( "%d", &v[i] );
}
/* "pointer" version */
void readVector2 ( int * v, int n ) {
	printf ( "Enter %d numbers:\n", n );
	for ( int * p = v; p < v + n; p++ )
		scanf ( "%d", p );
}
```

Both of these are entirely valid. Compiler will compile into more efficient option, so you just pick whichever one you prefer...

## Dynamic Memory Allocation
Main use of pointers in C is to handle output parameters in functions, to pass array to a function, to manipulate arrays (mainly strings), to access dynamically allocated memory.
A dynamically allocated object (variable) is not created using a declaration. Instead, the program controls its creation in the run-time, using a set of special functions (operators).
A dynamically allocated variable does not have a name. An address (a pointer) is used to access the variable.
C provides `malloc` function to allocate variables dynamically: the function takes one parameter – the size (in bytes) of the allocated variable, the function reserves a block of the requested size in the main memory, the function returns a pointer (an address) of the prepared memory block, the returned pointer is of void* type, it is usually needed to typecast the returned pointer.

Dynamic allocation of primitive data types is seldom needed: primitive data types are small, the overhead of the memory manager is far bigger than the size of the block itself. 
Dynamic memory allocation is useful when allocating bigger variables – arrays or structures. An example: a function reads the content a vector of given size n.

Is dynamically allocated block memory initialized?
The contents is undefined (not initialized), the contents is likely to be all-zero bytes for the first few memory allocations, however, this IS NOT guaranteed. 
Use `calloc` instead of `malloc` if your program insists on zero-filling.

Function `malloc` is a regular function in the standard library.
The interface is: `void * malloc ( size_t size );` 
Returns value is void*, i.e., a generic pointer (points to some data of unspecified type). If `malloc` is used directly, the pointer types will not match. Must be typecast.
