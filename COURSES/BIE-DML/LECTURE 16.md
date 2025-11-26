[[LECTURE 16 - PART 2]]
Finishing with counting principle for test 2
# Finishing Combinatorics & Probability

### Probability Space 
in situations where the chance plays its role, i.e. in situations for which we cannot determine the outcome for sure, we can use a probability space to model them.
A probability space is any triple $(\ohm, F P)$ such that:

$\ohm$ - an arbitrary nonempty set called the sample space. It represents the set of all possible outcomes $\omega$ (called elementary events) of an experiment.
$F$ - a set of subsets of $\ohm$ (i.e. $F \subseteq P(\ohm))$. Its elements are called events. Not that events consist of elementary events.
P - a mapping that assigns to each event from F its probability, which is a number from the interval $<0,1> = \{x \in R: 0 \leq x \leq 1\}$ , i.e. $P: F \rightarrow <0,1>$ Probability of a given event.

F and P must satisfy some properties.
The classical probability space is any triple $(\ohm, F, P)$ such that:
$\ohm$ - a finite, non-empty set.
$F$ - is the set of all subsets of $\ohm$ 
$P: F \rightarrow <0,1>$ given by $$\forall A \in F: P(A) = \frac{|A|}{|\ohm|}$$
Number of favorable outcomes over the number of all outcomes.

Note that if A and B are two events, i.e. $A, B \in F$ then
$P(A \cup B) = P(A) + P(B)$                    if A, B are disjoint, distinct
$P(A \cup B) = P(A) + P(B) - P(A \cap B)$ otherwise, principle of inclusion exclusion (IN-EX)

In the context of classical probability we also use the following terminology.
$\ohm$ is called the certain event (we have$P(\ohm)=1$)
$\emptyset$ is called the impossible event (we have $P(\emptyset) = 1$)
For any $A \in F$, we call $\overline A = \ohm$ \ $A$   the complement event of A, and its probability is
$P(A) = 1 - P(\overline A)$

A simple example of a probability space is the experiment of rolling a die.
The omega consists of all possible outcomes (1, 2, 3, 4, 5, 6)
$P(\omega) = 1/6$ for every elementary event $w \in \{1,2,3,4,5,6\}$
Denote A the event "an odd number was rolled" that is $A = \{1, 3, 5\} \subseteq \ohm$
Then, $P(A)=\frac{3}{6} = \frac{1}{2}$

Denote B the event "the rolled number was greater than or equal to there", that is $B = \{3, 4, 5, 6\}$ Then, $P(B) = \frac{4}{6} = \frac{2}{3}$

We will not require appendix for tests or exams, and maybe we could use some of it in our studies.