[[COURSES/BIE-PA1/LECTURE 11 - PART 2]]
### Integer Data Types - Continuation

Integer data types may be assigned values different from its data type. If a floating point is assigned to an integer, the value is converted first, e.g. fractional part discarded. If the result cannot be represented in the target type, the behaviour is undefined. There are different cases when an integer value is assigned to an integer variable.
If the value can be represented, it is assigned. If not and the target is unsigned, a value is stored such that it is equal to the original value modulo $2^N$. If the target type is signed, the behaviour is implementation defined (raising a signal is allowed)
The rules are reasonable, but the results may be surprising.

Due to the limited space to represent data, number datatype can't represent all values in any number system, where ven the smallest one (natural numbers) is infinite.
Precision and range for floating point numbers and range for integer numbers is finite leading to some unexpected behaviour.
Even associativity is not guaranteed. For integers, overflow is the bottleneck, and the precision mantissa rounding error for floating points.

For example,
```c
med(a,b,c) = a + b + c - min(a,b,c) - max(a,b,c)
```
With integer, it will overflow and then underflow, so it's okay.
However, for signed integers, the flow behaviour is undefined.
For floats, the associativity is problematic and so there will be a rounding error.
Repeated addition accumulates the error. Generally:
$$\exists a, b : (a/b) * b\neq a$$
Instead of $\sum_0^n 0.1$ it's better to use $0.1 * n$.

Likewise, approximations with trigonometric functions such as sine and cosine will result in errors. $sin^2x + cos^2x = 1$ does not hold in code, because of the trigonometric approximation and squaring.
Likewise, a + 1 > a holds for every a. However, with sufficiently big enough fractional number, the value of 1 is so small that adding it does not make a distance.
Likewise, $a > b \lor a = b \lor a < b$ is not true for situations where you may encounter NaN.