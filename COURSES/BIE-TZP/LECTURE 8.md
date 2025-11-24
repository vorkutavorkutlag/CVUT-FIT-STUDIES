# Implementation of Logic Gates

It is possible to implement all logic gates within electrical circuits.
Implementation of inverter, NAND and NOR will be discussed.

Logic values are represented by voltage.
If $0\leq0\leq u_{decision}$ then $log0$ (logically equivalent to zero)
If $V_{dd}\geq u \geq u_{decision}$ then log1 (logically equivalent to one)

![[Pasted image 20251124094527.png]]

As a revision, let us reminder ourselves of the voltage divider.
![[Pasted image 20251124094542.png]]
Here, $V_{dd}$ is the supply input voltage of the voltage divider

![[Pasted image 20251124094655.png]]
![[Pasted image 20251124094704.png]]
![[Pasted image 20251124094734.png]]

Then, let us replace $R_2$ by a two-state element. 
The two states include $R_2 = 0 \ohm$ and $R_2 = \infty \ohm$ , for log0 and log1 respectively.
It could perhaps be a switch (N switch or P switch).
Being a wire switch, it could either have no resistance at all when closed, or infinitely as much resistance when open, as no current can pass through.
We can control the switch by ourselves using unipolar transistors as switches.
![[Pasted image 20251124095906.png]]
When it is 'open', it behaves like a closed wire. When it is 'closed', it behaves like an open wire.

![[Pasted image 20251124100109.png]]
Alternatively, we can explore normally close switches.
![[Pasted image 20251124100250.png]]
They behave the same logically, although opposites.




## Implementation of an inverter
The inverter, taking log0, converts it to log1, and taking log1, converts it to log0.
It negates the evaluation. Then, with an NMOS transistor, being a normally open switch, we may implement it as such:
![[Pasted image 20251124100500.png]]
![[Pasted image 20251124100615.png]]
![[Pasted image 20251124100629.png]]

Then, let's explore PMOS inverters. Which, are symmetrical, but except the logic is a little different to accommodate for the fact they are normally closed.
![[Pasted image 20251124100811.png]]

We always use the formula for the voltage divider to derive the value.


## NAND Implementation

Let us remember switches in series. Every single one of them has to be open for the current to pass through. Then, we may chain switches (PMOS transistors) in parallel inside a resistance divider to implement a logical conjunction.

