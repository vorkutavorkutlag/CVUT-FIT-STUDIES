[[LECTURE 19]]
## Multidimensional array

#### Static
If matrix size is known in compile time, the matrix can be allocated statically.
```c
constexpr int ROWS = 3, COLS = 2;
int mat[ROWS][COLS];
```
The compiler serializes the matrix into memory in a row-major order. Rows are stored adjacent to each other, and each element in a particular row is also stored adjacent to each other.

We shall pass a pointer ot the beginning of the matrix to pass such matrix into a function. IT is indeed an array of 3 element, each element being an array of 2 elements, thus we shall pass a pointer pointing to an array of two elements.

#### Dynamic
Dynamic allocation shall be used if matrix size is not known in compile-time. Individual rows are allocated as 1D arrays, reference to the rows are stored in an auxiliary array. Passing it around will be defined with pointers to pointers. Freeing them would involve freeing the inner pointers first, and then the outer ones.

## Program Memory Map

Memory management is very complex in nowadays computers. The OS must consider the following requirements:
- virtual memory 
- paging
- segmentation
- memory mapped I/O
- memory shared among processes
- dynamically linked libraries
- threads, stacks per thread
- DMA, TLS, etc.

Memory management will be in-depth discussed in BIE-OSY.
Programs nowadays run concurrently and share the memory safely with one another. Memory from one program does not leak from one to another, and we should know how this technique of sharing memory works.
It is built on the concept of virtual memory. From their point of view, they still think they are the only ones running on your computer. It simplifies the perspective for them immensely, even if complicating it for the OS and CPU.
Virtual Memory is told to several programs at once that it belongs to them, and once a program finally does use it, it is then locked and kept to that program. This is because programs usually demand more memory than they actually use, and so this is a workaround.

Global variables occupy memory for the whole program execution time. Thus, do not use them for temporary data. The size of global variables cannot be changed in runtime. Thus global variables are not a good choice for data that may be large/small depending on the input. If allocated as the maximum, the program will always require a large amount of memory, even for small inputs. Global variables are useful to store constant and pre-calculated read-only tables. Stack is not a good choice for large variables, the limit is small thus do not allocate large data as local variables. Due to the LIFO allocation, local variables cannot be used if a reference to the variable shall be returned to the caller. Large variables shall be allocated dynamically on the heap.

# Complexity

Property of algorithm (not of the implementation of the algorithm!)
It is not measured in experiments, instead, algorithm analysis is used to establish complexity.
The complexity is measured as a function of the input problem size. The unit is not time. The complexity is measured as the number of operations performed.
It does not depend on the implementation, programming language, or underlying computer hardware. Another important algorithm property is space complexity (memory requirement).

The exact computation to the last operation is usually very difficult. The average case is usually the most difficult. Therefore, we often limit ourselves to the worst case computation. Moreover, we are usually not interested in the exact number of computations, rather their order.
The multiplicative concept in front of the `n` can be taken out, as for big data it becomes irrelevant. $O(999999n)$ is more efficient complexity than $O(n^2)$.

### Bubble Sort

Compare all adjacent elements in the array. If the two elements do not follow the order, swap them. Repeat this until all adjacent pairs are in the correct order. 
It follows the order $O(n^2)$ .

### Select Sort

Find the smallest element in the remainder of the array. Swap the smallest and first element. Repeat the previous steps, with the array one element smaller.