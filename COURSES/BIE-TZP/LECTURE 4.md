## Wolfram Mathematica

The mathematical software for calculation, solving and graphical representation.
To download it use the Wolfram User Portal.
* Log in to the Wolfram User Portal (https://user.wolfram.com/portal)
* Download the product
* Activate the product using SSO authentication (https://support.wolfram.com/54713)
It is recommended to install Mathematica on your laptop/PC.

When Mathematica is not available, Wolfram cloud might be used as an alternative. Note, it does not allow uploading files. 

It is important to launch the normal version and not the Kernel.

Creating a new notebook using File -> New -> Notebook and pressing Enter, it creates a new cell. Every cell can use a different style, e.g.: input, output, text, title.
Use Alt + Enter to create another cell. Due to Mathematica using Client - Sever model, calculations only get evaluated after using Shift + Enter (Numerical Pad).

In Mathematica, whole, rational, irrational and complex numbers are exact. Any involvement of real numbers makes the calculations approximate.


There are a plethora of functions in mathematica, for examples N[expression] will evaluate the expression in numerical form, as opposed to, for example $\frac{5}{2}$, it will write $2.5$.
Equally, if making one of the numbers a floating point, it will have the same effect (minus the small rounding errors)
Pressing esc, you may find constants and other variables, such as pi, if you write esc + p; esc + i + i will evaluate as the imaginary number.
You may find a math assistant to avoid using the shortcuts.

Use the link to the Mathematica Tutorial on moodle vyuka to look at more examples.
Note: You will need Mathematica to open the information/tutorial file.

```
ClearAll["Global`*"];
```
 To clear the variable information.
 `Clearall[x, y];` to clear specific variables

Another example for functions, `sin(x)` does not work but `Sin[x]` works.
To define functions by yourself, for example:
```
sigomid[x_, g_] := 1/(1+e^(-x+g))
```
Ctrl + / to do a fraction. Look at the informational file in the tutorial for more shortcuts, for example, exponentiation. In Mathematica it should look like:$$\frac{1}{1+e^{-x+g}}$$

To graph it, you could use the Plot function.
`Plot[sigmoid[a + 1, 1], {a, -10 10}]`

The first parameter is the function which we want to plot, and the second is the range of the chosen independent variable as a list containing the variable name, min and max values.
To plot in three dimensions, use `Plot3D` where the first parameter is the function, and second and third are once again ranges for the two independent variables containing the variable name, min and max values. For example:
`Plot3D[Sin[0.5*x] + 2*Cos[y], {x, -10, 10}, {y, -10, 10}]`


Mathematica also supports data structures similar to those from programming languages such as lists, which allow to group multiple elements and items together. It could be a string, a number, or mixed types. `First[mylist]` returns the first element, which in this language's case, is the first index. 


The main purpose of Wolfram Mathematica for TZP is the solving of lienar equations.
You may use the Solve function for this.
`Solve[{4*x+2*y==0, 5*x-6*y==5}, {x, y}]`
First list is the functions, second list is the unknown variables. Make sure to use double equations, as single equations are interpreted as assignments.

To solve differential equations, you may use DSolve (Differential solve) and also NDSOLVE (result describes plot of the function using interpolating function).

To solve the following equation: `x'[t] + Cos[t] = 0`
`DSolve[{x[t] + Cos[t] == 0}, {x[t]}, t]`

The second parameter of Dsolve is the list of unknown functions, while the third is an independent variable, that is: the variable that is inside the brackets of the unknown functions.
Solution contains constant which can be removed by inputting an initial condition to the system of equations. The equations themselves can give us a shape of the resulting function, but its precise position is given by initial conditions
See Solving Differential Equations page in the informational file.

Derivatives of user defined functions can be done using an apostrophe:
`myFunction'[x]`

Integration is similar:
`Integrate[n * x ^{-1+n}, x]`
Should look like:$$Integrate[n*x^{-1+n}, x]$$
For a definite integral:
$$Integrate[e^{-x}, {x, 1, Infinity}]$$
$$\int_{1}^{\infty}e^{-x}dx$$

Wolfgram Mathematica has some premium features such as showing the mathematical solution step by step to achieve it. It is more reliable than ChatGPT due to the lack of hallucinations.