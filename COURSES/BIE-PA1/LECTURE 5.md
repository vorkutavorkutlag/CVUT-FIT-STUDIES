[[LECTURE 6]]
#### Compiling a C program

The main function may either receive no parameters at all or some parameters such as keyword. You can write it as `int main() {}` It has to be an integer for the main function. It will return zero if the program succeeded. Other exit codes otherwise.
```c
int main() {
	return EXIT_SUCCESS;
}
```
`EXIT_SUCCESS` is a constant equal to zero to signify the program succeeded.

If no quotation marks are written around a string, the compiler will treat it as a variable, and usually fail to compile
```c
int main() {
	printf(Hello world!);
	return EXIT_SUCCESS;
}
```
INTO
```c
int main() {
	printf("Hello world!");
	return EXIT_SUCCESS;
}
```


Additionally, we need to include the library for the input/Output, as well as for the constants we use.
```c
#include <stdio.h>
#include <cstdlib>

int main() {
	printf("Hello world!");
	return EXIT_SUCCESS;
}
```

In order to compile a program, we may use IDE's or compilers such as gcc. The main method is to replace the C compiler with a C++ compiler, as C is almost a subset of C++. Thus, we should limit ourselves and avoid wild constructs that C has, that C++ lacks. The C++ compiler is more strict, and reports more errors that are not technically errors in C but are most likely to be a fault. Better at debugging.

To call a C++ compiler, use the command `g++` instead of `gcc`. It is usually called with the flags `-Wall` (WARN ALL, enable warning messages) and `-pedantic` (). 

An error will not allow your program to compile and is usually fatal, whereas warnings indicate that the program can indeed be compiled but it contains risks that the programmer should fix.

After the program is compiled and you have an executable, you technically don't need the source code anymore and can use the executable. However, you should always keep it around, for updates, debugging, etc.

The compiled program consists of bytecode, i.e. machine code with instructions to the program on how to execute it. It is possible to view it with text, or using a hex editor to read its elements (magic bytes, strings, etc.).

It can also be viewed as the assembly code through `objdump`, wherein we can inspect interesting elements of it; the exact instructions to the machine, the specific function calls and different optimizations. (The average PA1 student should not bother.)

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int a = 1234;
	int b = 6.23e23; // 6.23 * 10 ^23 EXPONENTIATION
	char c = 'e';
	const char * s = "some string"; 
	// a pointer to an array of characters. * signals it is a pointer already!
	// I cannot stress this enough. s is a pointer.
	
	printf("a=%d\n", a);
	// % is a special character for the printf function, not for the compiler.
	printf("a = %d = %x = %o %10d = %08d", a, a, a, a, a);
	// Representations in integer, hex, octal, padded space and 0 respectively.
	printf("b = %lf\n", b);
	printf("b = %lf = %le = %.0lf = %100.50lf\n", b, b, b, b);
	printf("c = %c", c)
	printf("s = %s", s) // receives pointer
	
	
	
	return EXIT_SUCCESS
}
```

Very often, floating point mistakes occur. 6.23e23 gets computed and exponentiated into: 623000....0010485760.0000. Notice how there are numbers that we did not input near the decimal point. Since floats are stored in binary, their conversion into very precise decimals is difficult, and some of these problems become apparent, especially when multiplied by large numbers.

**Segmentation fault** happens when an instruction is executed that results in a failure in the memory of the program, after which the operating system stops the execution of the program.

For example, trying to format on the basis of a wrong address could result in this.
%s expects a pointer as an input, which it receives with the pointer s, however if we feed it the value of a, it will try to look at the address 1234, which is usually reserved by the system.

```

Given a value x, &x gives an address.
Given an address y, *y gives a value.
```

Casting an integer into a float is sometimes necessary, for example, for more accurate divisions. (20/10 = 0 in integer math). It is possible by the following ways:
```
// Given an integer a
1.0 * a
(float)a
```
