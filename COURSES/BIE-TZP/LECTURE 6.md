# Circuits With Transistors

### Transistors
A transistor is a semiconductor element used to amplify and switch electrical signals and power. There are two main types of transistors, those being...
Bipolar: current sources and switches are controlled by electrical current.
Unipolar: current sources and switches are controlled by electrical voltage.
![[Pasted image 20251027110801.png]]
![[Pasted image 20251027110910.png]]

#### Bipolar Transistor
A bipolar transistor allows a small current injected at one of its terminals to control a much larger current flowing between two other terminals, making the device able of amplification or switching. Three terminal electrical elements: Base (B), Collector (C), Emitter (E).

#### NPN Transistor
In an NPN transistor, a positive voltage $U_c$ is given to the collector terminal and current $I_c$ flows from the collector to the emitter. As you increase the current to the base of the NPN transistor, the transistor is turned on more and more until it conducts fully from collector to emitter.
As you decrease the current to the base of a NPN transistor, the transistor turns off less and less, until the current is so low, the transistor no longer conducts across collector to emitter, and shuts off.

#### PNP Transistor
In a PNP transistor, a positive voltage is given to the emitter terminal and current flows from the emitter to the collector, given there is a sufficient negative current flow from the base. As current flows out from the base to the ground, the transistor is on and conducts across to power on and output load. As you increase current to the base of a PNP transistor, the transistor turns on less and less, until the current is so low, the transistor no longer conducts across and shuts off.

#### What's the difference?
Both NPN and PNP are bipolar transistors. BT (bipolar transistors) are current controlled transistors that allow current amplification.
NPN and PNP are exactly the same in their function, they provide amplification and/or switching capability, so technically, they achieve and do the exact same thing.

The base of an NPN transistor must be connected to positive voltage for current to flow into the base. In a PNP transistor, current flows from the base (negative current to the base) by giving the base terminal a more negative (lower) voltage than what is supplied to the emitter terminal. As long as the voltage at the base terminal is lower than at the emitter terminal in a PNP transistor, negative current effect will be achieved.

NPN transistor requires a positive current to the base, while a PNP transistor requires negative current to the base.
Another concept of differentiating NPN and PNP transistors is that since voltage is allocated differently, they have opposite current flows at the output. In an NPN transistor, output current flows from the collector to the emitter. In a PNP transistor, output current flows from the emitter to the collector.
That is why only circuit with NPN transistor analysis is discussed.

#### NPN Common Emitter Connection
![[Pasted image 20251027113538.png]]
![[Pasted image 20251027113602.png]]
![[Pasted image 20251027113628.png]]
![[Pasted image 20251027113659.png]]

![[Pasted image 20251027114509.png]]

#### Power Dissipation
In the transistor, you multiply the current going through it by the voltage dropped between the Emitter and Collector terminals, this gives you the amount of wattage that the transistor is 'wasting' and has to dissipate in the form of heat. If the transistor is off (not conducting), while there is voltage, there is no current so the dissipation is 0 Watt.![[Pasted image 20251027114554.png]]

