[[COURSES/BIE-PA1/LECTURE 14]]
#### Statically allocated arrays

An array is an ordered collection of values. It is declared using square brackets `[]` and initialized with curly brackets `{}`. It can be made multidimensional by staking square brackets `[][]`.
An array is a continuous block of memory, and every element in the array 'lives' next to each other and it is spaced equally.
To define an array with n elements, given a constant unsigned n:
```c
int array[n];
```
Such a condition holds:
```c
array[0] == *array
```
An array is simply a pointer with a bound (limit of the array) It is an address.
likewise,
```c
array[n] = *(args+n)
```

#### Structures
It is possible to create your own data structures using the fundamental types of the C language. For example, to create a structure for a fraction, we will use the syntax:
```c
struct fraction {
	int numenator;
	int denominator;
}
```
To create a type:
```c
typedef struct {
	int numenator;
	int denominator;
} fraction_t
```
You may access the variables inside the struct with the dot operator.
```c
printf("%d / %d\n", frac.numenator, frac.denominator);
```
