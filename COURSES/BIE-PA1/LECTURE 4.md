[[LECTURE 5]]
## VARIABLES, BASIC INPUT/OUTPUT IN C


### Bit, Bytes, Memory
=================
- Bit - the smallest piece of information that can be stored. Value is either 0 or 1. Easy implementation in a real world (high or low voltage, bi-stable flip flop, charged or discharged capacitor, etc).

- Byte - typically 8 bits. 2^8 = 256 different values. A processor may typically access bytes, not individual bits.

- Address - a unique identification of a byte in a memory: ordinal number of a byte (the position of a byte), counter from the beginning (of a memory space, of a memory chip, etc.)

- Capacity - the total number of bytes available:
	- Metric: 1KB = 1000B, 1MB = 1000KB = 1000000B, 1GB = 1000MB, etc.
	- Binary based (IEC 60027-2): 1 KiB = 1024B, 1 MiB = 1024 KiB, 1 GiB = 1024 MiB, etc



- Main Memory - stores program and data during computation (RAM).
	- Very fast, volatile (data lost after shut-down), expensive.
- External Memory - disk, CD/DVD, tape, etc.
	- Several orders of magnitude slower, non-volatile (data is not lost on shut-down), more complicated access to data, cheaper.



The computer, machine code, operates with bytes. It has exact rules on how to process bytes, and lacks any type of human understanding - it is a strict algorithm that processes data without respect to the values fed to it.
Users, humans, need to store information (integers, decimals, characters, strings). Information must be coded into bytes to be stored in memory. Coded information may permit only some operations (e.g. string would not permit square root).
High level programming languages usually provide a type system. 
**A type** represents some kind of information (number, string, etc.). It defines a set of possible values, a set of permitted operations, and coding (how to store the information in bytes, how many bytes does the information needs).

A high level programmer does not have to care about the underlying information representation. Information is stored in variables, which may accommodate different kinds of values. They typically have some **data type**, the type cannot change during the variable lifetime. 
For example, `int` data type in a C language implementation may have: the set of values in the range (-2^31 to 2^31-1) (32-bit)
The valid operations are:
- arithmetic operations (+, -, \*, /, etc.)
- relational operations (<, <=, \==, etc.)
- assignment operations (=, +=, etc.)
Programming languages typically have a few built in data types (e.g. int). Other data types may be defined by the programmer.


#### Variables
A variable is a named data object which contains some value. Moreover the value stored in a variable may change during the lifetime of the variable. Variables are defined by their names - unique identifiers. Variable declaration in C Language:
```c
int alpha;
/* alpha is the name of the variable */
printf("%d\n", alpha)*
/* \n adds a newline */
```
An assignment may be used to change the value stored in a variable.
`alpha = 20;`
Assignment operation is not an equality. It is an assignment to an expression.
`alpha = alpha + 1` (alpha is 21 now)


C allows you to declare a variable without specifying its value. However, using an uninitialized variable in the program will lead to the program not working properly. If it is not initialized, it could be several things instead usually. By default it could be zero, or some random value from RAM. Most compilers warn you about uninitialized variables.

##### `printf` Function
The library function `printf` can be used to print a fixed string, the content of variable(s) (with or without user-defined formatting), or evaluate the expression and print its value.

##### `scanf` Function
Standard `scanf` function reads characters, e.g., keystrokes from the keyboard, and converts them, storing them into variables.

##### Example:

```c
#include <stdio.h>



int main () {
	int x;
	
	printf("Enter a number:\n");
	scanf("%d", &x);
	/* note the pointer & */
	printf("The number was %d\n", x);
	return EXIT_SUCCESS
}
```

For the int data type, `scanf` skips any whitespace characters found in the input (spaces, newlines, tabs). It tries to read the value, starting from the first non-whitespace character. For int data type, the first character must be either a decimal digit, + sign, or -sign. It reads all characters representing decimal digits, and while the numbers are read, binary representation of the number is stored in the designated variable. Reading stops on the first value which cannot be added to the value. It can read two values "at once" (one after the other).

If there are not any characters in the input, the function simply waits for characters. The input into scanf is processed only after the user presses the Enter key. The OS buffers the input until Enter is hit, and passes the whole line to the process. scanf has a return value of the number of successful conversions it made. If it is equal to the number of conversions it was tasked to do, then all of them were successful. 
If scanf is called at end-of-file the function simply fails to read the variables and returns the number of successful conversions (which is strictly less than the number of required conversions in this case). Note that even standard keyboard input may signal end of file for instance when the input is redirected from a file or when a keyboard interruption key is pressed (CTRL-D, CTRL-Z, etc.).
If scanf fails to convert input erroneous characters into the prescribed data type, it does not remove the characters from the input. This behaviour may lead into an infinite loop if scanf is used incorrectly.

As for undefined behaviour, the C norm is if the result of the conversion cannot be represented in the object, the behaviour is undefined. Therefore, scanf (like atoi) cannot be securely used to parse numbers. The only secure option is to use strtol and its variants, however, it is complicated and laborious.Common scanf implementations silently ignore errors arising from input numbers outside of the integer range. We will use scanf despite the above limitation.

Thus, in practicality, it is important to ensure secure input handling in any code written by a programmer. That is, ensuring the correct type, the expected range, and any other parameters that are essential to the functioning of the program. [Input Sanitization]
Programs require valid input data to work correctly. Common nowadays vulnerabilities (buffer overflow, code injection, XSS, etc.) are indeed special cases of insecure input handling. Insecure input handling costs billions dollars every year. Secure input handling is boring and laborious. Alas, you still do it.

<small>You are required to write input sanitization in every piece of work.</small>


### Integer Data Types in C

C23 requires integer data ttypes to have some minimal rangers of representable values. The actual ranges can be larger depending on the implementation. The exact ranges can be found in system header files (limits.h, float.h, etc.) - e.g.,
`INT_MAX, INT_BITS`, etc.

![[Pasted image 20250929152529.png]]

The `bool` data type is considered to be an unsigned integer type but it has special conversion rules. 
Data type `char` may be either with or without a sign. Compiler authors are free to choose. Usually, it is signed (gcc, clang, mvsc, etc.)
char, signed char, and unsigned char are three distinct data types.

The system header file stddef.h defines the data type size t which is an unsgined integer data type large enough for size of any in-memory object. Its size is usually 32 or 64 bits (the norm requires at least 16 bits) and it is an alias for some other unsgined type.
The reason for this flexibility and lenient requirements is the accent on the portability of C across different architectures. 
There are small types, e.g. short int, to significantly reduce memory requirements when the processing data that naturally exists in huge quantities (pixel colors, audio samples, textures, depth maps, etc.)

The maximum of unsigned type is twice the maximum of a signed type. Unsigned types are used when the value is naturally non-negative (e.g., the number of elements in an array). A signed type may not be enough here - a 32 bit CPU may typically use up to 2^32 bytes of memory, thus it may store up to 2^32 elements. However, a signed integer may access only about half of them.
In cases of a need for integers of a specific length, use declarations from stdint.h, e.g., int16_t for 16 bit signed integer, uint_16 t for 16 bit unsigned integer, . . . These types are aliases for the corresponding built-in integer types, e.g., uint_16 t is typically an alias for unsigned short int

size_t is an unsigned integer, the range is big enough to store the size of the largest variable in the system may allocate, Typically the size of size_t is 32(4B) bits and 64(8B) bits respectively. 
Data type char is used to represent characters. Use unsigned char / signed char (or even better, int8 t / uint8 t) to represent 8 bit numbers (if you really, really, really need it).

- Use int type for general computation. Use long long if you expect really big numbers. Use size t to represent the number of elements (e.g., in an array). Use integers with guaranteed size (uint16 t, uint32 t, . . . ) for I/O operations with binary data (files, packets, . . . ).


Integer Literals:
- decimal: 123, 45678,
- hexadecimal: 0x123Ab, 0X569Fd (starts with 0x or 0X),
- octal: 0123, 0765 (starts with 0),
- binary: 0b1110 (starts with 0b or 0B),
- unsigned: 1234u, 5678U,
- long: 1234567679L, 1234567679l,
- unsigned long: 87654321Lu, 8321lu, 8321LU, 8321lU,
- long long: 1234567890123456LL, 0x1234ll (but not 123Ll),
- digits can optionally be separated by apostrophe ’.


### Character Data Types in C

Characters are coded as numbers. Many character encoding standards are used:
- ASCII (7 bit), 128 codes, US charset only.
- ASCII extended (8 bit), upper 128 codes for national characters.
- UNICODE (up to 2^20+2^16 characters) different byte coding (e.g. UTF-8)
- EBCDIC (8-bit)
The original 7-bit ASCII is common to all codes (except EBCDIC).
- 0-31 control codes (e.g. \n, 0x0A)
- 32 space (0x20)
- 33-127 symbols, digits, letters
- 48-57 digits (0x30-0x39)
- 65-90 A-Z (0x41 - 0x5a)
- 97-122 a-z (0x61 - 0x7a)

C language distinguishes characters and strings by apostrophes and quotes respectively. Non-printable characters may be written using escape sequences. Shorthand escape sequences for common characters:
- `\n` 
- `\t`
- `\'`
- ' "" '
- `\\`


### Character I/O
printf and scanf functions understand character conversion
%c. printf prints single character, based on the passed parameter. scanf scans the input for a single character and stores the code in the variable (char data type). scanf skips whitespace (spaces, tabs, newlines) for the number and string conversions (%d, %f, %s, . . . ). 
scanf does not skip whitespaces for the character conversion: %c reads whitespaces too, " %c" can be used to skip whitespaces before reading a non-whitespace character (space before %c), reading a single character via scanf is unnecesarily slow. It may be more efficient to use, for instance, getc. 

Note that C/C++ mixes characters (char data type) and tiny integer type (again char data type). Memory repr eprintf and scanf functions understand character conversion  
%c.   printf prints single character, based on the passed  
parameter.  
scanf scans the input for a single character and stores the code in the variable (char data type). scanf skips whitespace (spaces, tabs, newlines) for the number and string conversions (%d, %f, %s, . . . ). scanf does not skip whitespaces for the character conversion: %c reads whitespaces too,   " %c" can be used to skip whitespaces before reading a   non-whitespace character (space before %c), reading a single character via scanf is unnecesarily slow. It may be more efficient to use, for instance, getc. Note that C/C++ mixes characters (char data type) and tiny integer type (again char data type). Memory representation and computation is the same. Only input and output conversions differ.sentation and computation is the same. Only input and output conversions differ.


###### Formats
%x - unsigned integer
%d - signed integer
%c - character
%lf - float
%s - string

### Floating Point Data Types in C
Standard data types include:
- float - single percision
- double - double percision,
- long double - at least double percision
An approximation of real numbers. Limited range, and limited percision.
Properties of floating point data types are not specified in the C/C++ standard:
`sizeof(float) <= sizeof(double) <= sizeof(long double)`
Exact properties depend on implementation. 
Usually follow IEEE754. 

![[Pasted image 20250929155601.png]]

Floating point liters (constants):
- 1.25, 0.31, .47, 7.
- 1e6, -327e-15
Default data type of a floating point literal is double. The type of a floating point literal may be changed using the suffix f or l:
- 1.7f, 3f - float literal
- -2.6e+5l - long double literal.
Internal representation - semilogarithmic:
- base b, typically b =2,
- mantissa m, 1 <= m < b
- exponent e
- sign s, s ∈ {0, 1}

Mantissa specifies the precision. Though, then, you have less for the exponent. Give more to the exponent, you have less for the precision. The IEEE754 recommendation is as follows![[Pasted image 20250929155910.png]]
The +1b is based on the mantissa being: 
Normalizing the number in a way that the mantissa is always one point something by shifting it (changing the exponent), you will always have one in the front of mantissa, constantly, so that's why you don't need to store it, and that's how you get an additional bit that you can use.

Mantissa gives the precision of a floating point type.
$$decimals = \frac{mantissa\_bits}{log_210}$$