
1. Compute the [first-UIP](Unique%20Implication%20Points.md) [clause](Clause.md) $C$.
2. Traverse the [trail](CDCL%20-%20Conflict%20Driven%20Clause%20Learning.md#Decision%20Levels) $\tau$ backwards. For each [literal](AlgoSAT/Literal.md) $l\in C$ we attempt to remove $l$ from $C$ using [Self-Subsumption](Self-Subsumption.md) with the antecedent of $l$.

We could also remove $l$ from $l\in C$ while introducing new literals $l'$ to $C$ - if we knew that $l'$ can be reduced away later. We can do so efficiently using _implication chains_ $l_1\to l_2 \to\dots\to l_k$ where $l_1\in C$ and $l_k\in C$.

