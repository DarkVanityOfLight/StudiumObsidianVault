Let $G = (V, E)$. Let $V = R \cup C$ be a partition of $V$. We call $R$ the reason side and $C$ the conflict side.

We call $R \cup C$ a cut of the [Implication Graph](AlgoSAT/Implication%20Graph.md) $G$, whenever 
1. All decision literals are contained in $R$
2. $\bot$ as well as one conflicting literal is in $C$
3. There are no edges $x\to x'$ for which $x\in C$ and $x' in R$ holds.
We call an edge $x \to x'$ a cause of the conflict whenever $x\in R$ and $x'\in C$. The reason clause is formed by taking
$$\{\overline x | x\to x' \in E \text{ is a cause of the conflict}\}$$


The [first-UIP](Unique%20Implication%20Points.md) clause can be obtained by resolving antecedent clauses until exactly one literal from level $d$ remains. This is potentially not the only cut associated with the first UIP.