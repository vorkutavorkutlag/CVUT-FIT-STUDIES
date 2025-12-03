[[COURSES/BIE-TZP/LECTURE 4|LECTURE 4]]
# Fundamentals of circuit analysis

1. Basic connections of resistors, capacitors and inductors.
2. Fundamental laws of electrical engineering



### Combinations
#### Voltage sources

In series, they will be summed by their individual voltage sources with respect to their orientation. There is no need to connect the voltage sources in parallel, Connecting cells in parallel does not increase voltage. Voltage sources combined in parallel must have the same voltage i.e. we do not gain a higher voltage but can prolong life of the batteries.

#### Current sources

Kirchoff's law. Adding the values of the individual current sources with respect to their orientation. Similar to vector addition.

#### Resistors

When in series, there is a single, constant current that flows through all the circuits. The total resistance R of a serial combination of n resistors i given by algebraic sum of individual resistances R_1... R_n.
$$R = R_1 + R_2 + R_3 + ... + R_n = \sum_{i=1}^{n} R_i$$
They can be simplified into one big resistor and treated as such. (Except, voltages in-between differ)

When in parallel, every resistor is connected to the same voltage, but the individual resistances are different. There is more than one continuous path for electrons to flow and two groups of electrically common nodes (junctions). Inverse value of the total equivalent resistance R is given by the sum of inverse values of individual resistances.
$$\frac{1}{R} = \frac{1}{R_1} + \frac{1}{R_2} + ... = \sum_{i=1}^{n}\frac{1}{R}$$

Useful conclusions:
- When there are **two** resistors in parallel, that is equal to the product of their resistances divided by their sum.
$$R = \frac{R_1*R_2}{R_1+R_2}$$

- Any number of resistors in parallel, the resulting resistance is always less than each of the original resistances connected in parallel. (As there is more paths to flow)
Special cases:
- For N parallel resistors and each having the same resistance R, the total resistance R_T:
  $$R_T = \frac{R}{N}$$
- If one resistance is much less than another one connected in parallel with it, the total resistance is very nearly equal to the smaller one; if R_1 << R_2 then R_T ≈ R_1

#### Resistive Voltage Divider

A simple linear circuit that produces output voltage U_OUT that is a fraction of its input voltage U_IN. Voltage division refers to partitioning of input voltage across electrical elements (2 resistors connected in series) of the divider.
$$U_{OUT} = \frac{R_2}{R_1+R_2}U_{IN}$$
The formula is valid only and only if there is no load at the output terminals of the divider. U_OUT = loadless output voltage [V]. I_OUT = 0 [A] output current (for no load).

![[Pasted image 20250929101738.png]]

![[Pasted image 20250929101807.png]]

In case of a load, we use the voltage divided with a load. The divider output voltage U_OUT depends also on the resistance R_3 of the load it drives. In the voltage divider with load R_3, R_2, in the divider must be replaced by R_x that is a parallel combination of resistances R_2 and R_3.


![[Pasted image 20250929101830.png]]

### Resistive Current Divider

Simple linear circuit (parallel combination of 2 resistors) that produces an output current I_1(t) or I_2(t) that is a fraction of its input current I_(t). Voltage u(t) across resistors R_1 and R_2 is the same. $$R_1I_1(t) = R_2I_2(t)$$
![[Pasted image 20250929102052.png]]
Note that the proportion between the current's division is equal to that of the resistors strength. The stronger the resistance is, the less current flows through it, and vice versa.

### Capacitors
When in series, the inverse value of the total equivalent capacity C is given by the sum of inverse values of individual capacities. 
$$\frac{1}{C} = \sum_{i=1}^{n}\frac{1}{C_i}$$
In parallel, total equivalent capacity C [F] is given by the algebraic sum of individual capacities.
$$C = \sum_{i=1}^{n}C_i$$
### Inductors
In series, total inductance of L [H] is given by an algebraic sum of individual inductances.
$$L = \sum_{i=1}^{n}L_i$$
In parallel, the inverse value of the total inductance L [H] is given by the sum of inverse values of individual inductances.
$$L = \sum_{i=1}^{n}\frac{1}{L_i}$$
![[Pasted image 20250929130353.png]]


### Fundamental Laws of Electrical Engineering
Ohm's Law states that the el. current iR(t) through a conductor between two points A and B is directly proportional to the potential difference (el. voltage) uR(t) across these two points, and inversely proportional to the resistance R between them
$$i_R(t)=\frac{u_R(t)}{R}$$
Kirchoff's Current Law (1st law, `KCL`) states that the algebraic sum of all currents flowing into a junction (node) minus the sum of all currents flowing out of the node is equal to zero.
$$\sum{I_{IN}} - \sum{I_{OUT}} = 0$$
$$\sum{I_{IN}} = \sum{I_{OUT}}$$

Kirchoff's Voltage Law (2nd law, `KVL`) states that the algebraic sum of all voltages around any CLOSED LOOP in a circuit must be equal to zero. This is because a circuit loop is a closed conducting path so no energy is lost. Sign of voltage in the sum is given with respect to the direction of the chosen run around the closed loop.
$$\sum_{k=1}^{n}U_k = 0[V]$$
Note here that the term “algebraic sum” means to take into account the polarities and signs of the voltage sources and voltage drops around the loop.

- Moving around a closed loop, or circuit, you will end up back to where you started in the circuit and therefore back to the same initial potential with no loss of voltage around the loop. Hence voltage drops around the loop must be equal to any voltage sources met along the way.
- So when applying Kirchhoff’s voltage law to a specific circuit element, it is important that we pay special attention to the algebraic signs, (+ and -) of the voltage drops across elements and the voltages of sources otherwise our calculations may be wrong
- The orientation of voltage drop across a passive elements R, L, and C in the loop is the same as the orientation of the current flowing through these passive elements!!!