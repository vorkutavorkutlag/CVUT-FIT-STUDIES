[[COURSES/BIE-DML/LECTURE 10 (TUTORIAL)]]
# Sets and Mappings

In DML, we will be studying the practical aspect of sets, not pure set theory.
We will be using set operations and their properties to create sets from other sets.
We will show the connection to mathematical logic.
We will give precise instructions by mathematical logic.
Focus on formalism rather than intuition.


Set is an unordered collection of exactly specified objects. The fact that an element belongs to set M is denoted as $x \in M$.
A set that does not contain any element is called an empty set and is denoted by 0 or {}.

Informal attempts leads to paradoxes, e.g.:
Russel's paradox: Let M be a set of all sets x with property x not in x. Is then M in M? if M is in M then we have M not in M from the definition of M. Similarly, M not in M implies M in M.
Axiomatic set theory (Zermelo-Fraenkel) resolves the problem, but for us, the set theory is not a goal but a tool, so we will follow the so called "naive set theory"

To prevent paradoxes in the naive set theory, we always first choose some set U called **universe** and consider only elements and subsets of U.
Typical universes U include natural numbers ,non-negative integers, integers, rational numbers, real numbers, their subsets.

A set can be specified in either of the following ways:
- By explicitly listing its elements. e.g. A = {x, y, z}, B = {1, 2, 3, ... 20}, C = {2, 4, 6, 8, ...}
- by property characterizing its elements. e.g. $C = \{n \in N:$ n is even};
more generally, the set of all elements x of a universe U that satisfy property p(x) is denoted by $\{x \in U: p(x)\}$
- by an expression with a characterizing property. e.g: $C = \{2k: k \in N\}$
- inductively
- empty set

In literature, the notation might slightly differ.

Warning: There is no order or repetition of elements in a set! An element of universe either belongs to a set or it does not.

## Relations between sets

Consider sets A, B containing elements from universe U, then we define.
Inclusion, Equality, Proper subset, Trivial subset, etc.