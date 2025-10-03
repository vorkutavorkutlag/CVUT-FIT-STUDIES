[[COURSES/BIE-TZP/LECTURE 2|LECTURE 2]]
## Basic quantities and elements in electrical circuits
===================================================

Electrical Circuit.
- Closed path through which an electrical current can flow.
- Every component is a complex physical system.
- Studied as networks of ideal elements. Only dominant properties are taking into account whereas parasitic ones are ignored, therefore the behaviour description is not always accurate, and is merely an approximation of the real circuit.

Ideal Electrical Circuit
- The conductors have zero resistance.
- There is zero voltage drop across an ideal conductor
- No external magnetic fields

### Basic circuit quantities
===================

Electrical current.
EC is a flow of charge. In mentals, current is the movement of negative charge. i.e. electrons.
The unit of electric current is 1 Amper [A].
The average electrical current is defined as
$$I = deltaQ / deltaT$$
Q: charge of value [C]
T: time [s]
$$[A] = [C] / [s]$$
where deltaQ is the net amount of charge that passes through a cross section of the conductor during the time interval deltaT.
If the current is not constant in time, we can define instantaneous current as limit.
$$I = lim (deltaT->0) deltaQ/deltaT = dQ/dT$$
The charge of an electron is approximately 1.6 * 10^-19 C.
1 Amper = 6.2 * 10^18 electrons per second.

Current direction convention.
A flow of positive charges gives the same electric current, and has the same effect in a circuit, as an equal flow of negative charges in the opposite direction. Since current can be the flow of either pos or neg charges, or both, a convention for the dir of cur which is independent of the type of charger carriers is needed.
The direction of conventional current is defined to be the direction of the flow of positive charges. They flow from the (+) terminal toward the (-) terminal of the voltage source (from higher to lower potential).
In metals, which make up the wires and other conductors in most circuits, the positive charges are immobile, and the charge carriers are electrons. Because electron carries neg charge, the real electron motion in a metal conductor is in the direction opposite to that of the conventional.

In the hypothetical circuit piece [U1 - Resistor - U2] with current 10A flowing through it, potential at U1 is higher than at U2, therefore it will flow from U1 to U2.
You can also say *negative* current flows from U2 to U1, wherein its direction and sign are flipped. (10A becomes -10A, in the opposite direction)

## Current measurements
Ampermeter measures the positive electrical current going through a circuit. Ideally, it has very little to no internal resistance. Same goes for the voltmeter.

Voltage is defined as an electric potential difference between 2 points on a conductor.
$$Uab(t) = Ua(t) - Ub(t)$$
Sometimes voltage is described as electric pressure that makes current flow.
Measured in Volts [V] using a voltmeter.
Symbols for el. voltage: u, u(t), U
Voltage (diff in potential) vector between A and B is equal to that between B to A, with the sign of its magnitude flipped.

## Basic electrical elements, properties, symbols
### Elements versus components
There is a distinction between a real electrical or electronic components and the ideal electrical elements by which they are represented.
Electrical elements do not exist physically. They are assumed to have ideal properties.
Conversely, electrical components do exist, and have less ideal attribute. For example, an Ampermeter may have some form of internal resistance. All parasitic properties are neglected.

### Classification
Passive elements. In passive elements, the delivered energy is either converted into another form (heat) or stored in the created electric and/or magnetic fields. Passive elements are either absorbers or accumulators of energy.
Resistors (absorbs energy) [R] - [Ohm]
Capacitor (energy accumulator) [e]
Inductor (energy accumulator) [L]

- (current and voltage directions in passive elements are the same)

Active elements. Electrical energy sources that are able to permanently deliver electrical energy to a connected electronic circuit.
Voltage sources
Current sources

- (current and voltage directions in active elements are opposite)

Active can change the direction. Passive cannot change the direction.

Ideal voltage source is independent and indifferent to the current that flows through it, and has an internal resistance of zero. It is able to supply any amount of current. Thus, an ideal voltage source can supply unlimited power.
Denoted by `U`
No real voltage source is ideal; they all have a non-zero internal resistance, and none can supply unlimited el. current. However, the internal resistance of a real voltage source is effectively modelled in a linear circuit analysis by combining a non-zero resistance in series with an ideal voltage source.

Real voltage source equation:
$$U = U0 - Ri * I$$
U... voltage on the real voltage source terminals.
U0... Voltage of the source when the circuit is open, i.e. the source has no load.
Ri.... Resistance of the load.
I..... El. current flowing through the resistor(s)


Circuit electrical current flow
$$I = U_0/(R_i+R_z)$$
Resistance at a point
$$u = I*R_z$$

Ideal voltage feeds the same volts no matter the el. cur. through it.
Hard voltage feeds almost the same, but due to the resistance, albeit small, falls off with the amper.
Soft voltage, due to the strong resistance, feeds less voltage with more el. cur.

When connecting in series,
The sum of all (potentials of) voltage sources is zero.

There is no reason to connect batteries (vol. sources) in parallel. Vol sources in parallel must have the same voltage ie we do not gain a higher voltage but can prolong life of the batteries.

As opposed to that, you can connect electrical current sources in parallel, resulting in the use of **Kirchoff's law (KCL)**. $$I_3=I_1+I_2$$
Swapping the sign of the current vector makes it possible to connect currents, albeit they will become negative during calculation 
$$I_3=I_1-I_2$$

You cannot connect electrical currents in series, as it will result in the sources failure.

### Three basic passive (linear) two-terminal elements:
- Resistor R, resistance measured in Ohms Ω - produces a voltage drop uR(t) proportional to the current iR(t) flowing through the element (resistor). It relates voltage uR(t) and current iR(t) ] according to the relation (Ohm ´s law):
$$u_R(t) = R * i_R(t)$$
- Capacitor C, capacity measured in Farads F - produces a current iC(t) proportional to the rate of change of voltage uC(t) across the element (capacitor). It relates current iC(t) and voltage uR(t) according to the relation:
$$i_C(t) = C * \frac{du_C(t)}{dt}$$
- Inductor L, inductance measured in Henrys H - produces a voltage uL(t) proportional to the rate of change of current iL(t) through the element (inductor ). It relates voltage uL(t) and current iL(t) according to the relation:
$$u_L(t) = L * di_L(t)/dt$$
![[Pasted image 20250922130559.png]]

![[Pasted image 20250922130645.png]]
![[Pasted image 20250922131732.png]]

### Resistor R
$$R = p * l/s$$
Where `p` is the resistance of the specific material, l is the length of the resistor, and s is the surface area of the face. 
$$u_R(t)=R *i_R(t) $$
The Ohm’s law expressed in words: current through a metal conductor is
proportional to the applied voltage. This means that R is considered a
constant, which is valid in case of metal wires or resistors, but we cannot
use the Ohm’s law for semiconductor elements, light bulbs and other
devices, which are called nonohmic or nonlinear.

### Capacitor C

Capacity is ability of a body to hold an electrical charge. Capacity is so a measure of the amount of electrical energy stored for a given electric potential and is measured in Farads (F).
A common form of energy storage element is a capacitor.
A capacitor (originally known as a condenser) is a passive two-terminal electrical element used to store electrical energy in the form of electric field created by a voltage between two conducting surfaces (e.g., metal foil) called “electrodes” and separated by an insulating material called a “dialectric”
$$i_c(t) = C * du_C(T)/dt$$
It is necessary to know initial condition uC(t0)=uC(0) at initial time t0=0 s to solve the differential equation. Usually, the initial condition uC(t0)=uC(0)=0V

### Inductor L
Inductors store energy in the magnetic field created by current flowing through a wire. The capacity of the majority of inductors used in electronic circuits is several orders of magnitude smaller than one Henry. The most common subunits of inductance in use today re subunits nano-Henrys (nH), micro-Henrys (μH), milli-Henrys (mH) etc. Inductors are made of wire wound in a coil, sometimes around a core made of magnetic material that concentrates the magnetic energy.
For a linear inductor, the fundamental relation between el. voltage uL(t) across the element and el. current iL(t) through it is:
$$u_L(t) = L * di_L(t)/dt$$
It is necessary to know initial condition iL(t0)=iL(0) at initial time t0=0 s to solve the differential equation. Usually, the initial condition iL(t0)=iL(0)=0A
### Material classification
- Conductors have very low resistance, that can usually be neglected.
- Insulators have every big resistance that can usually be omitted from circuit for analysis. We can replace them by disconnections.
- Resistors have a medium range of resistance and must be taken in the account for the circuit analysis.
