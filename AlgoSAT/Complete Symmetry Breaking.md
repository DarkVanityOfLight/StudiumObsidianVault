Let $\Gamma \le Sym(V)$ be a permutation [group](Gruppe.md) over some [set](Mengen.md) of [variables](Variable.md) $V$. A boolean circuit $C$ with $Var(C)\subseteq V$ is called _complete_ [Symmetry](Symmetry.md) breaking for $\Gamma$, whenever for each orbit $O$ of complete assignments under $\Gamma$, there is 
- A $\gamma \in O$ such that $C[\tau]$ is true
- For all $\tau'\in O$ with $\tau \not = \tau'$ the formula $C[\tau']$ is false
