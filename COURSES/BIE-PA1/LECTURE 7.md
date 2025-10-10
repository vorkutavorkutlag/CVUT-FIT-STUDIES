[[LECTURE 8 (LAB)]]

The lecture began by finishing the previous proseminar's function, which was a basic calculator and handling invalid input. The solution was to clear the standard input after each invalid input.
```c
while (scanf("%c", &x) == 1 && x!= '\n') {}
```
This could be used to clear it. Additionally, it is possible to use a flush function, but it is not portable, so this approach is more sophisticated.

What followed was an exercise involving writing a function that, given three sides of a triangle, to return if the triangle was a right triangle or not. It started by finding which of the sides was the hypotenuse - the biggest side was the hypotenuse. Then, compare the sum of the squares of the other two sides with the square of the biggest side, the hypotenuse.

We discussed the dangers of floating point values. For example, the squares work with the numbers: 12, 35, 37. However, they fail with: 1.2, 3.5, 3.7. That is because we can only represent values that are either a bit smaller or a bit bigger than a number, usually. 1.2 is never really equal to 1.2, however, 3.5 and 3.5 are always equal to each other because it's a half fraction. These are called rounding errors. 
When handling values that are close to the ideal values, but not equal, performing computation with them brings us close to the ideal result, but not quite. It is not 100% identical, and so, the comparison fails, because RHS and LHS does not match.

One of the solutions to this issue is adding an epsilon (error margin) to 'forgive' some level of mistakes. It is usually a really small number, like `1e-9` and solving this equation instead:

```c
|a*a + b*b - c*c| <= epsilon
```

A better choice would be on the property of floating point numbers. 
A floating point number is represented by the sign, mantissa and exponent.
$$(-1)^{s} m 2 ^{e}$$
Mantissa is clamped by 1.000...0, and 1.111...1. With a fixed amount of bytes.
The rounding error is usually rooted in the least significant bit in the mantissa.
<float.h>
`DBL_EPSILON` is the ratio of the least significant bit and the most significant bit. In some cases it is about 2^-52, and can be used to help with the difference. It is equal to the rounding error. If you do any operations on the floating points, you must do similar operations on the epsilon. i.e. if you square the floating points, the error margin definitely grows - so you must account for that when you use the epsilon error margin.

This fails us when we deal with extraordinarily small numbers or likewise extraordinarily big numbers. 1e-100 1e-100 1e-100, and 3e100 4e100 5e100. The epsilon is either way too big or way too small in both cases. The solution is multiplying the epsilon by the order of our input, multiplying it by an average variable that is around the magnitude of the variables are dealing with.
This gives the epsilon some proportion.

It is important to play with floats properly so you may be able to do proportional operations on it.
For example, if x is computed by some x = a - b, and then you see if x == 0, you may not use the epsilon for x.
|x - 0| <= epsilon \* |x|
This is just a really complex way of writing x == 0. Instead, you should do:
|a - b| <= epsilon \* (|a| + |b|)

The second part of the lecture included writing a maximum, minimum, and average finding program. The main highlight was the addition of tests - where the programmer would write text files of input and expected output, and then write a bash script to run the executable and compare them automatically. i.e.:
```sh
#!/bin/bash

# For every file that adheres to the regular expression digit digit .txt
for input in [0-9][0-9].txt ; do
# 
	./a.out < $input > /tmp/out 
```