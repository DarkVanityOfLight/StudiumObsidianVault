---
aliases:
  - unit
  - Unit
---

A [Clause](Clause.md) is _unit_ if it has only one literal, the only way to satisfy this clause is to set the literal to $\top$. 
Removing falsified literals, can produce unit clauses, satisfying unit clauses until fixpoint can be expensive.

_Unit propagation_ makes unit clauses true until fixpoint.
Given an [Assignment](Assignment.md) $\alpha$ and a [Formula](Formula.md) $F$, unit propagation extends $\tau$ by assigning all unit clauses in $\alpha\circ F$ to $\tau$.

We can reach two possible fixpoints:
- $\alpha\circ F$ contains a falsified clause $\bot$.
- $\alpha\circ F$ contains no more unit clauses

Unit propagation is the heart of the SAT solver, it can take up to 90% of the computation times.


Let $F$ be a formula, a clause $C$ is implied by $F$ via unit propagation if UP on $F \land \neg C$ results in a conflict via [Resolution](AlgoSAT/Resolution.md).

