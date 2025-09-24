
In the beginning, the professor recounts the elementary formulas and propositions, and the connectives (Conjunction, Disjunction, Implication, Equivalence).
What followed was a series of simple examples, such as:
`W: Wednesday, M: Monday, C: Class, A: Has Cat, O: Has Dog, B: Barks, D: Dog`
1. Today it's not Wednesday: neg W
2. We don't have a class today: neg C
3. Today it's Wednesday and we have a class: W and C
4. Jane has a cat and a dog: A and O
5. Jane has a cat but she doesn't have a dog: A and neg O
6. Jane has a cat or a dog: A or O
7. If an animal barks then it's a dog: B implies D
8. An animal barks only if it's a dog: B implies D
9. An animal is a dog only if it barks: D implies B
10. We have a class today unless it's Monday: neg M implies C
11. Today is Wednesday if and only if we have a class: W is equal to C

Additionally:
`T: Tram, S: Subway`
1. I take the tram and the subway: T and S
2. I take the tram or the subway: T or S
3. I take the tram if and only if I don't take the subway: T equivalent to neg S
4. I take the tram or subway but not both: (T or S) and neg (T and S)
5. Unless I take the subway, I don't take the tram: Neg S implies Neg T
\* Last one can be also written as T implies S


Following, truth tables were discussed. A can be either 1, or 0; B can be either 1, 0; Their comparison creates 4 options:
- A: 0, B: 0
- A: 0, B: 1
- A: 1, B: 0
- A: 1, B: 1
neg A: 1, 1, 0, 0
A and B: 0, 0, 0, 1
A or B: 0, 1, 1, 1
A implies B: 1, 1, 0, 1
A equals B: 1, 0, 0, 1

Sidenote: 1 implies 1, 0 implies 1 and also 0 implies 0. 1 does not imply 0.
			Similarly, a truth can be implied from a truth, a truth can be implied from a lie, a lie can be implied from a lie, but a lie cannot be implied from a truth.

Next, satisfiable and insatisfiable formulas were discussed, as well as tautologies and contradictions. (Every insatisfiable formula is a contradiction)
- (neg A implies B) or A: creating a truth table for this by splitting it into subformulas and filling it in by the possible values of A or B manually. If the result per every case is true, it is a tautology. If only some, then it is satisfiable. If none, then it is a contradiction.


The truth table of a tautology has only one row, being true (1).
The truth table of a contradiction has only one row, being false (0).

When two formulas share a truth table, they are logically equivalent.
As in, for every possible case (every possible variation of the 'variable' [A, B, C, etc.]), if the two truth tables are identical, then the formulas are logically equivalent. For example, a formula consisting of A and B with the truth table of [0, 1, 1, 1], and a differently written formula also consisting of A and B with the truth table of [0, 1, 1, 1]], are logically equivalent to one another.

There is a difference between the connective equivalence and the logical equivalence.
(F is equal to G) is a new formula (7+4=11)
(F is logically equivalent to G) is a comparison (7=?4)
Practically they are very, very similar, but formally they are different.

Necessary and sufficient conditions:
A is a sufficient condition for B whenever the occurrence of A is all that is needed for the occurrence of B. 
B is a necessary condition for A whenever A cannot occur without the occurrence of B.
C, A
C => A: 
A => C: 
A <=> C: It is necessary and sufficient to be 18 to drive a car


###### - If the equivalence between two formulas is not a tautology, then the two formulas are not logically equivalent. This equivalence can be measured with a truth table.

This can be used to find some properties of connectives. For example, 
$$((A=>B) => C) <=> (A => (B => C))$$
Can be found to be a satisfiable formula, but not a tautology. Therefore the implication connective is not distributive.
This was done by filling an 8-row truth table of A, B, C with every possible combination of theirs (2^n, 2^3 = 8). Manually filling it and evaluating the expressions of the subformulas, slowly building up to the final expression (the overall formula).
With the same method, we found a tautology:
$$(A => (B=>C) => ((A => B) => (A => C)))$$

However, truth tables are not always the most efficient way to solve problems. We prefer to use logical laws in order to replace formulas with their logical equivalents. An example of those laws are ***De Morgan Laws***:
1. neg (F and G) |=| neg F or neg G
2. neg (F or G) |=| neg F and neg G
	(Conversion between a conjunction and disjunction)