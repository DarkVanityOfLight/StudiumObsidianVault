---
aliases:
  - UIP
  - First-UIP
  - first-UIP
---
[Unique Implication Point](Unique%20Implication%20Point.md)

assume we have a conflict variable $x$ in an [Implication Graph](Logik/Implication%20Graph.md) $G_d$. We look at the conflict subgraph $H = (V, E)$ of $G_d$ containing
- $\bot$ and exactly one conflict variable $x$
- all nodes of $G_d$ which have a path to $x$ or $\neg x$.


A node $u\in V$ with $lev(u) = d$ is a _unique implication point_ iff every directed path from the decision literal $dec_d$ to the conflict node $\bot$ passes through $u$.

Among all UIPs, at level $d$, the _first-UIP_ is the one closes to $\bot$ along any path.

The first-UIP clause can be obtained by resolving antecedent clauses until exactly one literal from level $d$ remains.
The backjump level is the _second highest_ decision level appearing among the remaining literals of that learned clause.

