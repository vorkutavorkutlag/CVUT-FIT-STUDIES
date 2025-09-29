[[LECTURE 4]]
#### Numeral Systems
==============
In our day to day lives we used the decimal system, which consists of 10 numbers:
0, 1, 2, 3, 4, 5, 6, 7, 8, 9.
The most primitive machine code that is used by computers is written in the binary system, which consists only of 2 numbers:
0, 1.
You can represent any decimal number in a binary format and vice versa.
Conversions from decimal numbers to binary numbers have multiple methods. The most simply method is manually converting every decimal/binary point.
For example, the number 45 can be represented as `101101`.
It is a combination of powers of 2.
`100000` = 32
`1000` = 8
`100` = 4
`1` = 1
32+8+4+1=45, 100000+1000+100+1 = 101101 Q.E.D -> 45 = `0b101101`.

Similarly, you may convert binaries to decimal forms by looking at the placement of the 1's and 0's and giving them powers of 2 respectively of their index.

There is an additional, more efficient method.
Given a decimal numbers, divide the number by 2. If there is a remainder, push 1 to the right side of the new binary number being created. If there is no remainder, push 0 to the right side of the new binary number being created. Repeat the process until the number becomes `1`.
For example:
100%2 = 0 -> 0
100/2 = 50
50%2 = 0 -> 00
50 / 2 = 25
25 % 2 = 1 -> 100
25 / 2 = 12
12 % 2 = 0 -> 0100
12 / 2 = 6
6 % 2 = 0 -> 00100
6 / 2 = 3
3 % 2 = 1 -> 100100
3 / 2 = 1
1 % 2 = 1 -> 1100100

Q.E.D 100 = `0b1100100`

The inverse is the efficient way to convert binaries to decimals is going from left to right. The sum starts from zero. If you encounter `1`, add 1 to the sum, if you encounter `0`, add nothing. Each time you shift to the right you multiply your sum by two..
`0b1011`
(1) \* 2
(2+0) \* 2
(4+1) \* 2
(10 + 1) => 11
Q.E.D `ob1011` = 11 


Another popular base in computer science is base16, also called Hexadecimal. The conversion methods are similar to the ones discussed in the binary section, albeit slightly more complicated due to the number of bases.


8-bit systems have a minimum of 0 and a maximum of 255 if they are not signed.
In the case that they are signed, they have a minimum of -127 and a maximum of 127. 
'Signed' indicates a bit is used for plus or minus, to indicate the sign of the number. It's the leftmost number in big-endian systems. Alternatively, in little-endian, it is the rightmost number.

To switch the sign, convert to binary, flip all the bits, add 1. (??)