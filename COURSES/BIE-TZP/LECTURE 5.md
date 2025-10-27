[[COURSES/BIE-TZP/LECTURE 6|LECTURE 6]]
## DIRECT CURRENT

### DC CIRCUITS
Within electrical engineering, a DC circuit (Direct Current circuit) is a DC powered electrical circuit i.e. powered by any combination of constant voltage sources, and/or constant current sources.Of course, the DC voltage sources and DC current sources are supposed to be ideal.

### DC READY STATE
After connecting the DC power supply to the circuit that contains inductors and/or capacitors), after a certain time (after the transients in the circuit disappear), the circuit reaches the so- called DC steady state. Transients occur even when the source is disconnected. In the DC steady state, the circuit quantities are stabilized and no longer change. This only happens in circuits that contain some capacitors and/or inductors.
![[Pasted image 20251020092320.png]]

### Capacitors, Inductors

For resistive circuits, the voltage-current relationships are linear and algebraic (Ohm´s law for every individual resistor). Resistors can only dissipate energy; they cannot store energy and return it to a circuit at a later time.

This is NOT the case for capacitors and inductors. Capacitors and Inductors are dynamic elements. The voltage-current relationships of ![[Pasted image 20251020092855.png]]capacitors and inductors are differential. They are dynamic because they store energy.

AS a reminder,
#### Capacitor
$$i_C(t) = C * \frac{du_C(t)}{dt}$$
Capacitor is a passive element designed to store energy in its electric field. This energy can then be provided to a circuit at a later time.
Capacitors consist of two conductors (parallel plates) separated by an insulator (or dielectric). Capacitors accumulate electric charge. Conductive plates can become charged with opposite charges.
![[Pasted image 20251020092650.png]]
![[Pasted image 20251020092701.png]]

While charging a capacitor, the voltage $u_C$ developed across the capacitor will increase as charge is deposited. The current goes to zero once the voltage developed across the capacitor is equal to the source voltage.
![[Pasted image 20251020092750.png]]

![[Pasted image 20251020092900.png]]

Note that the capacitor voltage will be equivalent to that of the circuit in the beginning.

![[Pasted image 20251020093558.png]]
After we switch the switch to position C, the capacitor starts supplying voltage, acts like a voltage supply before it drains. It generates it in the opposite direction. Maximum value $=\frac{U}{R}$ (Ohm's law).

As soon as the switch reaches position B, the circuit current rises very rapidly (Fig.1), as the capacitor begins to charge . Although the voltage is still low, its rate of change is large and the voltage graph is initially very steep, showing that the voltage is changing in a very short time. As the capacitor charges, the rate of change of voltage slows and charge slows as the charging current falls. The curve describing the charging of the capacitor follows a recognisable mathematical law describing an exponential curve until the current is practically zero and the voltage across the capacitor is at its maximum – source voltage U. If the switch is now changed to position C, the supply is disconnected and a short circuit is placed across C and R. This causes the capacitor to discharge through R. Immediately maximum current flows but this time in the opposite direction to the that during charging. Again an exponential curve describes the fall of this negative current back towards zero. The voltage also falls exponentially during this time, until the capacitor is fully discharged.

![[Pasted image 20251020094512.png]]
![[Pasted image 20251020094604.png]]

### Indcutor

$$i_L(t) = L * \frac{du_L(t)}{dt}$$
An inductor is a passive element designed to store energy in its magnetic field. – Inductors consist of a coil of wire, wound around a core.

![[Pasted image 20251020094805.png]]
![[Pasted image 20251020094852.png]]
![[Pasted image 20251020095038.png]]
![[Pasted image 20251020095146.png]]
![[Pasted image 20251020095633.png]]
You may substitute it by a short circuit, a conductor.

![[Pasted image 20251020095746.png]]

![[Pasted image 20251020095814.png]]

![[Pasted image 20251020100208.png]]

![[Pasted image 20251020100218.png]]


### Conclusion
The big thing to understand about capacitors and inductors in DC circuits is that they have a transient (temporary) response. During the transient period, capacitors build up charge and stop the flow of current (eventually acting like infinite resistors in DC steady state.) Inductors build up energy in the form of magnetic fields, and become more conductive (acting like ideal conductors with zero resistance in DC steady state). In other words, in DC steady-state (long term behavior following the transient response), capacitors become open circuits and inductors become short circuits. Thus, for DC analysis, you can replace any capacitor with a disconnection and replace any inductor with a short circuit. The only circuit components that remain in DC circuits are DC voltage sources, DC current sources, and resistors.

![[Pasted image 20251020100542.png]]

![[Pasted image 20251020100553.png]]


In the next exam we will need to describe nodal analysis. 