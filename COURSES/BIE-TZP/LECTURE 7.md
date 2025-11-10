## Basic Logic Gates

### Boolean Logic

The two element boolean algebra is used for circuit design in electrical engineering. Here 0 and 1 represent two different states of one bit in a digital circuit, typically high and low voltage. In digital circuits, logic values 0 and 1 are used for binary coding of numbers and mathematical operations. Also, for two valued logic as TRUE and FALSE and logic operations.
Boolean logic, is a subset of algebra used for creating true/false statements. Boolean expressions use the operations `AND`,` NAND`, `OR`,` NOR`, `XOR`, `XNOR`, and NOT to compare values and return true or false results. All of these take two or more inputs except NOT which takes one input.

Digital circuits described by boolean expressions containing binary variables. 
computer logic can be often expressed in Boolean terms. 
Computer processors perform complex calculations by linking multiple binary (i.e. Boolean) statements together. Complex Boolean expressions can be expressed as a series of logic gates.


![[Pasted image 20251110102641.png]]

Let us explore the notations and truth tables of the logical gates.


![[Pasted image 20251110102828.png]]
The circle at the end of the gate usually denotes inversion.

![[Pasted image 20251110102903.png]]
This can be viewed as multiplication. Only when is multiplied by 1 is it 1.

![[Pasted image 20251110103038.png]]
NAND - Not And, is the inverted truth table of AND. 
NAND is a complete logical set.

![[Pasted image 20251110103154.png]]
Either A or B have to be true.
Can be viewed as addition.

![[Pasted image 20251110103237.png]]
NOR means Neither A nor B.

![[Pasted image 20251110103333.png]]
One of the special functions is XOR, exclusive OR. A OR B and NOT (A AND B)
This implies A and B are not equal.

![[Pasted image 20251110103540.png]]
The negation of NOR, implies A and B are equal.

### Some notes
AND and OR gates can have more than 2 inputs, by chaining logical operations right after the other.


## Boolean Arithmetic
Let us explore boolean arithmetic of addition and multiplication.
- Boolean addition: any logic value added with 1 is 1, and any logic value added with 0 remains unchanged. Therefore the OR operator is sufficient.
- Boolean multiplication: any logic value multiplied by 0 is 0, and any logic value multiplied by 1 remains unchanged. Therefore the AND operator is sufficient.

### Boolean identities
#### OR
The first Boolean identity says that the SUM of any logic value and zero is equal to the original logic value. This Boolean identity is not different from its real-number algebraic equivalent. A OR 0 is $A \lor \bot$ which is equivalent to just $A$.

The next identity is definitely different from any seen in real number algebra. Here we discovered that the sum of any logic value with one is equal to one. 
A OR 1 is $A \lor \top$ which is A.

Next, we examine the effect of adding A and A together, which is the same as connecting both inputs of an OR gate to each other and activating them with the same signal.
$A \lor A \equiv A$ 
In real-number algebra, the sum of two identical variables is twice the original variable's value (x + x = 2x), but there is no concept of "2" in the world of Boolean math, only 1 and 0, so we cannot say A + A = 2A. Thus, when we add a Boolean quantity to itself, the sum is equal to the original quantity: 0 + 0 = 0, and 1 + 1 = 1.

#### AND
The first Boolean identity says that the MULTIPLICATION of any logic value and zero is equal to ZERO This Boolean identity is not different from its real-number algebraic equivalent $A \land \bot \equiv \bot$ 

The next identity says that the MULTIPLICATION of any logic value AND one remains unchanged. This Boolean identity is not different from its real-number algebraic equivalent.
$A \land \top \equiv A$ 

The third multiplicative identity expresses the result of a Boolean quantity multiplied by itself. In real number algebra, the product of a variable and itself is the square of that variable. However, the concept of „square„ has no meaning in Boolean algebra, so we cannot say that $A * A = A^2$ 
Instead, $1 * 1 = 1 ; 0 * 0 = 0$ 

The forth multiplicative identity expresses the result of a Boolean quantity multiplied by its complement. $A \land \neq A \equiv \bot$

#### NOT
Another identity having to do with complement is that of the double complement: a variable inverted twice. Complementing a variable twice (or any even number of times) results in the original Boolean value. $\neg \neg A \equiv A$


![[Pasted image 20251110110115.png]]

![[Pasted image 20251110110155.png]]

![[Pasted image 20251110110208.png]]

![[Pasted image 20251110110831.png]]

## De Morgan's Laws
In Boolean algebra, De Morgan's laws is a pair of transformation rules that are both valid rules of inference. The rules transform the expression of conjunction (AND) and disjunctions (OR) purely in terms of each other via negation.
$\neg (A * B) = \neg A + \neg B$  and likewise $\neg(A + B) \equiv \neg A * \neg B$
The rules can be expressed in words as:
- The negation of a disjunction is conjunction of the negations, and vice versa..
- The negation of a conjunction is the disjunction of the negations, and vice versa...
It is possible to chain them.
$AB+AC+BC = \neg (\neg (AB) * \neg (AC) * \neg (BC))$ 



## Combinational Circuits Design
We can combine basic logic gates together for calculations. The resulting circuit is called a combinational circuit or just a gate. By combining gates, we can compute any boolean expression (logic function). This is how we build digital circuits that make up an ALU (arithmetic logic unit) and other parts of a computer. 
It is also, at times, possible to simplify a combinational logic gate.
