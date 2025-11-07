[[COURSES/BIE-PA1/LECTURE 10]]
The lecture continued by elaborating on the rules of the Gregorian leap years, and how to convert them into a simple algorithm using if statements and conditions.
It is important to note that there is an importance to the order of if statements. For example, an algorithm calculating how many digits a number from a given range has by comparisons, it is more efficient to first check the numbers of a higher order (5 digits), as there are a magnitude more of them than numbers of a smaller order (1, 2 digits).


### Loops in C
A while statement is a loop that repeats the statement as long as the condition is met, as it checks it time and time again after each iteration.
```c
while (condition)
	statement
```

Simple integer division and factorial computation can be done with this, as we do not know the given number of iterations.

do-while loop is similar to the while loop.
The only different is the condition, which is tested after the execution of the loop body.
```c
do
	statement
while (condition);
```

The main reason for using this instead of evaluating the statement and then starting the while loop is because the code is 'nicer'. It is more readable, understandable, and potentially more efficient. Following the D.R.Y principle (Don't Repeat Yourself).

Loops are often controlled by a variable where it is known. 
What is the initial value of the variable, what is the termination condition, and how to change the content of the variable in every iteration. Therefore, the designers of languages came up with a loop that binds together these elements:
```c
for (int i = 1; i <= n; i ++)
	statement
```
Initial declaration, the condition, the increment.

`for (init; cond; incr) statement` can be rewritten as:
```c
init;
while (cond) {
	statement
	incr;
}
```

They can be rewritten by one another.

The declared variables exist only for when the for loop runs, and they do not exist outside the loop, and do not collide with identifier i in the parental block or sibling for-loop.
At times they could be stored in the same place in the memory if the code is run in series one another the other, but in the language sense they are independent.


This can relate nicely into the previous themes. For example, finding a fixed number of data in the sequence, the length of the input sequence is given by a number entered prior to the sequence, and if the sequence is terminated by a sentinel (special value, EOF, etc.)

To detect the end of input without a custom sentinel (terminating when encountering a certain specific data), you may use the expression:
```c
feof(stdin)
```
The concept of end of input is natural to not eliminate valid data because you 'must' pick a sentinel. This expression will return true if the standard input as met the EOF.
Every program gets three files.
`stdin` - keyboard, if you do not redirect input
`stdout` - console, if you do not redirect output
`stderr` - channel for encountered errors

##### Break and Continue
For and While loops may be terminated before the loop body is entered.
Do-While loop may be terminated after the loop body is left.
If there is a need to terminate the loop inside the loop body (e.g., some error), break statement may be used.
```c
while (cond1)
	if (cond2) break;
```
The Continue statement starts a new iteration of the loop body.
```c
for (...) {
	if (cond2) continue;
}
```
It simply 'skips' the current iteration and continues iterating then on.


##### Finite and Infinite loops
Algorithms are terminating, i.e., all loops shall terminate.
An infinite loop is almost surely a mistake.
The value of variables participating in the loop condition must change in the loop body. If the variables are changed in the loop body, the loop may terminate. If they are not changed, the iteration never starts or iterates forever.


##### Flags
Simple technique to test single condition in a sequence of
elements (e.g., all even, all positive, etc. ). Designate a variable (a flag) and set it to true. Scan the sequence and test the condition for each element
##### Switch statement
Switch statement allows the programmer to split the execution into several branches as opposed to the if statement which branches off only in two branches. These branches are identified by an integer constant, and have the form:
```c
switch (expr) {
	case 1: statement1; break;
	case 2: statement2; break;
	case 3: statement3; break;
	default: def_statement;
}
```
If a break is missing, the control flow reaches another branch until a break or end of a switch is reached.


### Integer Data Types - Internal Representation

Typically programmers aren't concerned with how data is stored in memory and their representation, but, from time to time there is a task that would be more efficient with respect to the internal representation.
Unsigned values are stored in binary code.
Data types bigger than 8 bits occupy several consecutive bytes.
Byte order: little-endian (loh, Intel), big endian (hilo, Motorola).

unsigned int a = 1000;
1000 = 0x3e8 = 0011 1110 1000

In Little Endian:
1110   1000   0000 0011   0000 0000   0000 0000
e8 03 00 00

In Big Endian:
0000   0000   0000 0000   0000 00011    1110 1000
00 00 03 e8

These representations depict whether the data stored is 'flipped' or not. If it is, then the most significant byte and least significant byte (magnitude and order) switch places.


Signed values must keep the sign somehow - an additional code must be used.
2's complement is the most common.
in other codes, 1's complement, biased code, sign-and-magntitude code.
In 2's complement code, if the value is positive or zero, convert the value into the binary code, the binary code is the result.
If the value is negative, use the absolute value to omit the sign, negate (complement) all bits, then add 1 to the number.

--Output conversions--