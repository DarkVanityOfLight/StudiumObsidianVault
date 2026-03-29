
The most commonly used inference rule in propositional logic is the _resolution rule_, the operation denoted by $\bowtie$

$$\frac{C \lor x \quad D \lor \lnot x}{C \lor D}$$

Adding (non-redundant) resolvents until fixpoint is a _complete proof procedure_. It produces the  [empty clause](Clause.md) iff the formula is unsatisfiable.

If we resolve a clause $C$ from clauses in $F$, then $F \land C$ is [Equisatisfiable](Equisatisfiable.md) but not [Equivalent](Equivalence.md) to $F$.

The backward direction is triviall, $\alpha \vDash F\land C$ implies $\alpha \vDash F$. For the other direction assume $\alpha\vDash F$ and $C$ is obtained from $A \lor x$ and $\overline x \lor B$ in $F$. Then $\alpha\vDash A \lor x$ and $\alpha \vDash \overline x \lor B$. hold.
If $\alpha(x) = 1$, then $\alpha \vDash \overline x\lor B$ forces $\alpha \vDash B$
If $\alpha(x) = 0$, then $\alpha \vDash A \lor x$ forces $\alpha \vDash A$
Thus in either case, $\alpha \vDash A \lor B = C$ so $F \vDash C$.



## Resolution as Proof System
We can use resolution as a [certificate](Certifying%20Algorithms.md). To use this in an algorithm, we want to compute with resolution proofs, and thus need to store them, for example as a graph.

A resolution proof consists of all nodes and edges of the resolution graph.

We can reduce the size of the proof by only storing added clauses, clearly clauses whose addition preserve satisfiability are redundant, checking this redundancy should be efficient.