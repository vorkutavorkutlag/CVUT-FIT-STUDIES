
Use flag -02 when compiling with g++ to optimize the compilation.
Takes slightly more time.
## Binary Data

Worked on quick exponentiation algorithm by separating the exponent into powers of two and iterating over the individual bits by using the bitwise and and then bitshifting to the left to look at the 'next bit'.
```c
for (int i = 0b0000_0000_0000_00001; i<=n; i <<= 1 ) {
	if (i & n)
		res *= a;
	a *= a;
}
```