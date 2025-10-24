[[Lecture 13 (LAB)]]
## Binary Coding - Continuation

For n bits, there are $2^n$ possible unique values that can be represented in binary.
For a certain range, you need n=$log_2$ (range length) bits.
The length of the range is max limit minus min limit + 1.
For a certain range with a need for precision: $log_2(\frac{length}{precision}+1)$.

There exists an algorithm to convert decimal to binary.
It works because division by two is a bitshift in binary, therefore explaining the use of the quotient.
Symmetrically, you may convert from binary to decimal by multiplying 0 or 1 by $2^{index}$

There exists an algorithm to convert from every base to every other base.
However, in some situations, for example decimal fractions to binary, you may lack a way to represent it.

The mantissa is a fixed point number as opposed to a floating point.
Therefore, the definition for floating point numbers, $(-1)^s * m * 2^e$ is not flawed.
To convert a binary number into IEEE representation, it is need to concatenate them. The order is sign, exponent, mantissa.

Mantissa is always between 1 and 2. To represent zero, the greatest and lowest exponents are used, along with inf and NaN.

precision = $\frac{mantissa}{log_2 10}$
range = $2 * 2^{2^{exponent-1}-1}$
