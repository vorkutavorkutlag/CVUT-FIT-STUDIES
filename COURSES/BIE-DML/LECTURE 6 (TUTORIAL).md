[[COURSES/BIE-DML/LECTURE 7|LECTURE 7]]
First exercised was using the golden law and de morgan laws to convert $A \implies (B \lor C)$ into a formula using only $\{\neg, \land\}$ as it is a complete set. 

Today we will see that we can be even more precise than that.
Every formula can be rewritten in full DNF/ full CNF.
To this we can add universal bound laws with tautologies and contradictions, and also identity laws to turn those into variables, and then use distributive laws to distribute them across the terms, and so we can 'create' these variables out of 'thin air'.
We will always have 2^n valuations where n is the number of variables.

$(\neg A\lor \neg B \lor C)$ FULL CNF
$(\neg A) \lor (\neg B) \lor (C)$ DNF

Full DNF is DNF in which the terms between the disjunctions are CNF with all vars.
Full CNF is CNF in which the terms between the conjunctions are DNF with all vars.

These are increasingly useful in proving of logical consequences.

For example,
$(B \land \neg A) \equiv (B \land \neg A) \lor (C \land \neg C)$
Therefore,
$(B \land \neg A) \equiv (\neg A \land B \land C) \lor (\neg A \land B \land \neg C)$
