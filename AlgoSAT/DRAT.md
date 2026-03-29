
> [!Resolution Asymmetric Tautology]
> A clause $(C\lor x)$ is a resolution asymmetric tautology on $x$ with respect to a CNF [formula](Formula.md) $F$ if for every [clause](Clause.md) $(D\lor \overline x) \in F$ $C\lor D$ is implied by $F$ via [Unit Propagation](Unit%20Propagation.md).


> Let $F$ be a CNF formula and let $(C \lor x)$ be a RAT clause on $x$ with respect to $F$. Then $F$ and $F \land (C\lor x)$ are equisatisfiable.

Any model of $F\land (C\lor x)$ is clearly a model of $F$. 
For the other direction, suppose $F$ is satisfiable with $\alpha$. Assume $\alpha \not\vDash (C\lor x)$, then $\alpha(x) = \bot$ and all literals in $C$ are false under $\alpha$. Construct $\alpha'$ by setting $\alpha'(x) = 1$ and $\alpha'(y) = \alpha(y)$ for all $y\not = x$. Towards a contradiction, assume $(D\lor\overline x) \in F$ is falsified by $\alpha'$. Since $(C\lor x)$ is a RAT on $x$, the clause $(C\lor D)$ is implied by unit. In particular, every model of $F$ must satisfy $(C\lor D)$, since all of $C$ is falsified by $\alpha$ a literal of $D$ must be satisfied by $\alpha$ and as such, $E$ must be satisfied.

> DRAT and [Extended Resolution](Extended%20Resolution.md) are $p$-equivalent



