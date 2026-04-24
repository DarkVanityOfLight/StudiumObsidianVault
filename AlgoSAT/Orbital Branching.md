We take in account the [Symmetry](Symmetry.md) of the CNF for the branching rule.

Let $F$ be our [formula](Formula.md) of interest, $\tau$ the current partial [assignment](Assignment.md) and $\Gamma$ a group of symmetries of $F$.

Define $\Gamma' = \Gamma_{\{v\in Var(F) | \tau(v) = 0\}}$ and $\Gamma'' = \Gamma'_{\{v \in Var(F) | \tau(v) = 1\}}$ 
Intuitively Elements of $\Gamma''$ map the partial assignment $\tau$ to itself. Let $O_v$ be the orbit of [variable](Variable.md) $v$ in $\Gamma''$.
Then we recursively solve the two subproblems
- $\tau_0 = \tau \circ [v \mapsto 0]$
- $\tau_1 = \tau \circ [v' \mapsto 1 | v' \in O_v]$
