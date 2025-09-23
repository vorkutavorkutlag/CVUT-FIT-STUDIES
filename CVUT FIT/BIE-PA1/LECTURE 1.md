# INTROCUTION: ALGORITHMS & LANGUAGES

[[LECTURE 2]]

Algorithm by definition is a sequence of operation to solve a certain class of problems. Algorithm consists of a list of unambiguous commands. Algorithm guarantee that the desired final results are available for any admissible combination of input data.
Moreover, the results are available after a finite number of steps.
### Properties
- Universal - algorithms are designed to solve a certain class of problems, not just one particular problem instance. The particular problem instance is given by input data.
- Deterministic - each step in algorithm is unambiguously defined. There is no room for randomness or free will.
- Resultative - algorithm provides the desired results for any admissible problem instance.
- Terminating - algorithms terminate in a finite number of steps for any admissible problem instance.
- Input - the problem instance is described in the form of input data.
- Output - the desired results are provided in the form of output data.
- Complexity - we are usually interested in algorithms which are efficient with respect to speed (time usage) and space (memory usage).
### Expressions
- Natural language.
- Flow charts.
- Structure diagrams (Nass-Scheidermann diagram).
- Pseudocode.
- Programming language (e.g., C/C++/Java... etc.)

//few examples of algorithms and their optimizations//

### Abstraction
We usually do not show the complete algorithm when we are handling complex topics. Rather, we use black boxes, defined methods with an input and output that follow all the properties of an algorithm, and refer them by their name.

### Programming Languages
Low Level programming languages (assembler, machine code):
- very simple structure, designed for machine.
- elementary operations (e.g., move the content of a memory cell into a register, add two registers)
- difficult for humans, prone to make mistakes.
High level programming languages (C, C++, Java, Pascal, Ada, ...):
- designed for humans.
- programs are shorter, easier to understand.
- separates the programmer from machine specific technical details (memory organization, instruction set, machine word size)
- cannot be used by the machine directly (must be translated into the machine code first).

 
 Imperative languages (procedural programming style) (e.g., C)
	- a program is a sequence of statements, processed in a top down order.
	- loops and branches may be used to change the execution order.
	- subprograms may be called (changes execution order, reuses parts of the program)
	- return from a finished subprogram - immediately after the call command
Non-imperative languages (e.g., SQL)
	- functional programming style.
	- declarative programming style.
	- more on non-imperative languages in different modules (e.g., BIE-PPA).

Syntax - the formal way how to write a program.
Semantic - the interpretation.

Interpreted code is less efficient but can be used in more situations, whereas the compiled code is compiled per the specific machine it is ran on, which allows for specific optimizations.

C language advantages:
- high level programming language
- permits low level programming (address manipulation, pointers)
- optimizing compilers produce highly efficient machine code
- programs are portable among different platforms (if machine dependent tricks are not used)
- C syntax is used in many other programming languages (C++, Java, Perl, C#, JS)
C language disadvantages:
- questionable security policy - everything is left on the programmer
- no run-time checks (array indices, valid pointers)

C is almost a subset of C++, as there are only some C constructs that are not valid in C++. Mostly, C++ is based on C, and adds its own constructs.

PA1 module:
- program in C and use C constructs.
- avoid C constructs that are not valid in C++
- not use C++ only constructs (classes, templates, etc.)
- use C++ compiler (rigid checking).
- will be valid in both C and C++.