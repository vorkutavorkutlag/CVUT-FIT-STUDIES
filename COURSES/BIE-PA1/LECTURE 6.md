[[COURSES/BIE-PA1/LECTURE 7]]
#### Other data types include
##### Structure
A user defined data type which packs multiple values into a single object. E.g. struct {int a; double b;} s is a structure containing an int and a double. Its members are accessed by operation . (dot), e.g., s.a.
##### Array
A sequence of values of the same data type indexed by non-negative integers, e.g., int a[5] is an array of 5 ints. Its elements are accessed by operation [], e.g., a[2]

##### Pointer
An address in memory where a value of a pointed-to type is stored, pointers are denoted \*, e.g. int\* p is a pointer to an int value.

##### void
A type without a value

###### enum, union, etc.
Named definition, sharing a single memory space, and others...

## Expressions and conditions in C language
=============================================

Expressions are used to evaluate values of some type. An expression may contain variables, constants, function calls, operators, brackets, etc. Expression evaluation has operator precedence and operator associativity.
```
x + y * z -> x + (y * z) // * precedence is higher
x + y + z -> (x + y) + z // + is left-associative
x = y = 0 -> x = (y = 0) // = is right-associative
```

![[Pasted image 20251006145452.png]]

Arithmetic operators include:
division (/) - performed in an integer type if both types are integers, otherwise floats.
modulus (%) - reminder is defined for integers only. 
bitshift <<. >> - bit shifts are defined for integers data types.
```
x = a >> b; /* x = a / 2^b, fraction discarded */
x = a << b; /* x = a * 2^b, sign may be lost */
```

Padding example
![[Pasted image 20251006150510.png]]


##### Type conversions in operations

The higher or more capable data type participates in the operation. Operators, arithmetic, relational, may be used with different types. The data type of operands is unified before the operation starts. The conversions include:
if either operand is long double, the other operand is converted to long double.
else if either operand is double, the other operand is converted to double.
else if either operand is float, the other operand is converted to float.
else if either operand is unsigned int, the other operand is converted to unsigned int.
otherwise the operands are both converted into int.

Relational operators include: numeric (floating point & integer) datatypes, ordered - the value may be compared using relational operators. Comparison, result is int 1 if the relation holds, int 0 otherwise.
Mistake #1:
```
a = -10;
x = -100 < a < -1;
// -100 < a is evaluated first into (1). therefore, (1) < -1 is evaluated as 0.
```


Mistake #1:
```

a = -10;
x = -100 < a < -1; /* x = 0 */
/* x = (-100 < a ) < -1; */
/* x = 1 < -1; */
```
Mistake #2:
```
unsigned int x = 100;
int y = -1;
if ( x < y ) printf ( "oops\n" );
```
Combining datatypes is usually not a good idea.


#### Logical Operators
C did not have a specialized data type for boolean values (bool). Hence, int data type is still used for compatibility reasons. 0 – false, other values (different from 0) are true. 
Logical negation – ! The result is 1 if the operand is 0. Otherwise, the result is 0. 
Logical AND – &&. The result is 1 if both operands are nonzero. 
Logical OR – ||. The result is 1 if either operand is nonzero. The second operand is not evaluated if the result is determined by the first operand.

#### Bitwise operators
![[Pasted image 20251006152127.png]]


##### Increment and decrement
Unary operator with a side effect of changing the variable. Prefix or postfix notation:
prefix – ++x, --x. Increments (decrements) the value of x, the resulting value is new value.
postfix – x++, x--. Increments (decrements) the value of x, the resulting value is old value.

##### Conditional
The result depends on the condition.
`cond ? expr : expr2`
The condition is evaluated, if the condition is nonzero (true), the result is the value of the expression expr1. Otherwise, the result is of value expression expr2.
`max = x > y ? x : y`

##### Assignment
The operator does nothing to the value computed. However, it has a side effect, replacing the contents of a the left hand side operand with a new value. The operator is right associative.
```
int x; float y;
x = y = 1.34;
// y = 1.34
// x = 1

y = x = 1.34;
// x = 1
// y = 1.00
```

The assignemnt may perform some modifications of the value:
`+=, -+, *=, /=, %=, <<= ,>>=, &=, ^=, |=`

The standard math library `<math.h>` includes the following function/operations:
![[Pasted image 20251006154214.png]]

### Flow Control
__To control flow__:
sequences - statements are executed in a top-down order.
branches - one or more statements are executed only under a certain condition.
loops - one or more statements are executed repeatedly, absed on a certain condition.
__Implementation__:
structured programming - statements may be formed into blocks of statements, blocks may be used in branches and loops (C/C++/Java/Pascal,etc.).
"spaghetti code" - labels and goto statements (original BASIC).

Global declarations are declared outside any functions, outside the main function, same 'row' as the library importations. Local declarations exist within functions, and they overshadow the global variable. As in, when you try to access the variable by that same name, it will use the local one rather than the global one.