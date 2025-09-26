[[LECTURE 3]]
## Programming languages and styles


### Programming Paradigms

Example basis: $$(a+b) * (c+d)$$ 
#### Imperative

As a programmer, you must be very precise and specific with your instructions to the machine with very little to no abstraction. Such languages include Pascal, machine code, etc.
Algorithms most prevalent here.
- Example:
		
		add a+b
		add c+d
		mul
#### Functional
Heavily dependant on functions, at times lacking basic concepts such as variables, although including passive outputs of one function into another, which in some cases in more optimized. Haskell, Pascal, etc.
- Example
		`mul(add(a,b), add(c,d))`
#### Logical (declarative)
Generally convenient and abstracted, powered by declarative instructions. For example, SQL queries. Non-imperative style of programming in which programs describe their desired results without explicitly listing commands or steps that must be performed
#### Object Oriented
High level paradigm that structures software around objects, which are self-contained units that bundle data (attributes) and the code that operates on that data (methods). Rather than focusing on functions or logic, OOP models real-world entities, using classes as blueprints to create these objects, which then interact to form a complete program. Python, C++, etc.


### Primitive Elements
#### Basic elements:
- Entry point: only one, initial
- End point: only one, finishing
- Branches: suppressing some statements and choosing others, based on conditions.  
- Statements: computation and declaration
##### Derived elements:
- Loops ( = Branches + return somewhere)
- I/O operation ( = special statement)
- Invocation of another algorithm ( = special statement)

### Flowcharts Definition

![[Fig 15-Flowchart Symbols.jpg]]

Sidenotes:
\* Associativity in most programming languages is left-oriented. For example,
$$z/2*a$$
	would equate into $$(a*z)/2$$


Most processors use `IEEE754`'s definition and standard of mathematics. Upon encountering any type of mathematical lack of definition, such as a square root of a negative number, inverse-function of a value outside of the functions domain, etc. the processor will return `NaN` - not a number. It is neither equal to another instance of NaN, nor to any other primitive type or object. Division by zero results in either infinity or negative infinity, which acts only as a concept similarly to NaN. (`float.inf`) 


// gcd and lcm exemplary algorithms with modulus //