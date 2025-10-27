#### ...Structures and typedef
The keyword typedef is used to give an existing type another name. The new name is an alias, it still denotes the same type. typedef works with any type, not only structures. It cannot replace existing types.

```c
typedef struct MinMax MinMax_t;
typedef unsigned long long int ull;
typedef struct {int min, max;} MinMax2;

unsigned long long int a = 5;
ull b = a;
MinMax_t c = {4, 5};
MinMax2 d = c; /* ERROR */
```

Each definition creates a new distinct data type. Hence we cannot interassign `c, d`.

# Memory Allocation

Memory allocation is done by the compiler and the runtime environment. The problem is to assign addresses (reserve memory space) for variables.
Global variables are allocated in the data segment by the compiler (static allocation). The allocation is done once in the compile time and is fixed for the variable life time.
Local variables are allocated in the run-time. The variables are allocated as they are needed. When a function is invoked, the variables are allocated. When the function terminates (returns to the caller), the memory space is feed (and may be used by another function). This saves the memory as well as permits some programming concepts e.g., recursion).

Local variables are allocated in the **stack**, operating in LIFO (last in, first out) manner. When a function is invoked, its variables are allocated on the top of the stack. When the function terminates, the top of the stuck is decreased, thus the caller's variables appear on the top of the stack.

An interesting phenomenon appears when a value goes out of scope and another uninitialized value is declared in the same 'hierarchy' in the code. It is assigned the address that was just freed and, while not initialized, might give the value of the freed variable.

# Complexity

...prime number calculation is always exponential as opposed to computation of maximum in a list, which is linear. 
I hoped he would discuss Big O Notation, but not yet.

# Arrays

An array of type T is declared as `T p[n]`, where T is the type, p is the identifier variable name, and n is a positive integer. When uninitialized, a global array would have a content of all zeros, and a local array would have undefined data. You may access the `i-th` element of an array by `p[i]`.
if i is a positive value and i is smaller than the number of elements in array p, then `p[i]` is a variable of T data type
The indexing has bounds.
If the index does not fit in the index range, then `p[i]` refers to ”some” place in the main memory. An operation (read/write) may have fatal consequences (abnormal program termination, data overwritten, data lost, etc.)
Indexing outside of array bounds is not checked in run-time. The behavior is undefined, and may very from OS to compiler. Out of bounds array is difficult to debug.

Arrays may be used to represent a mapping. The mapping may assign values to integer indices. For example - read a sequence of integers and establish a frequency table for numbers in the interval 1-100, inclusive. The table will contain 100 elements of int data type. The value `frq[x]` will denote the number of occurrences of number x+1. The table will be declared as a global array. Therefore, the elements will be set to zero at the beginning.

Another niche is that arrays, since they work as pointers, if they are passed to a function as argument, and the function modifies them, the changes will be saved to the actual array.
A function declares array parameter with T element type in either of the two variants:
```c
T arr[]
T * arr
```
Both options are equivalent from a syntax point of view, as well as from the implementation point of view. The parameter may be an array of any length. The function does not know the length of the passed array. The parameter arr does not have that information. Indeed, the parameter only denotes the address of the array in the main memory.
`sizeof(arr)` will return the size of the pointer, not the size of the array itself! 
If the function needs to know the actual number of array elements, another parameter representing the number of elements must be passed

# Strings

String literal is a sequence of character enclosed in quotes. They are represented as an array of characters in the memory, where each element has data type char. The string is is terminated by the zero char (zero byte).
String variables will hold the characters. `char mystring[n]` will hold `n-1` characters, as one variables is needed for the termination.
String operations may be called from the `<string.h>` library. Some important functions include:
1. `strcpy` - copy a string (unsafe)
2. `strcat` - append a string (unsafe)
3. `strcmp` - compare two strings
4. `strlen` - the length of a string
5. `strncpy` - copy a string (safe)
6. `strncat` - append a string (safe)

A common pitfall – the unsafe variants do not test whether the resulting string fits into the destination array. If the string is too long, memory is overwritten!



...On the proseminar, we discussed optimisations of a pascal triangle function. The main task was to avoid overflow.  Logarithmic division (zigzag division to not get big numbers), simplifying mathematics (polynomial formula can be rewritten as $\frac{m(m-1)(m-2)...(m-k)!}{k!}$) , mirroring the outputs as they were symmetrical, playing with equations, i.e.:
```c
(*res * (n-1) > INT_MAX)
// Can be rewritten as:
(*res > INT_MAX * (n-1))
```
