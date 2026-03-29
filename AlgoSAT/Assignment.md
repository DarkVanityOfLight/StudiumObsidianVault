---
aliases:
  - assignment
---

An [assignment](Bewertung.md) $\alpha$ is a partial map from [Variables](Variable.md) $Var(F)$ to values $0, 1$. 
Applying the (partial)assignment to $F$, written as $\alpha \circ F$ results in a new reduced formula, with all satisfied clauses removed, and all falsified literal removed.

- $\alpha$ is a _satisfying assignment_ iff $\alpha \circ F$ is empty
- $\alpha$ is a _falsifying assignment_ iff $\alpha\circ F$ contains $\bot$
