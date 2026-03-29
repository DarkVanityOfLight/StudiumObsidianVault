A [clause](Clause.md) $(C\lor x)$ is blocked on $x$ with respect to $F$ if for every clause $(D\lor \overline x)\in F$, the [resolvent](AlgoSAT/Resolution.md) $C \lor D$ is a tautology.

Adding or removing a blocked clause preserves satisfiability.

Let $(C\lor x)$ be blocked on $x$ in $F$. $F$ and $F \cup \{C \lor x\}$ are equisatisfiable.

Clearly any model of $F \cup \{C \lor x\}$ also satisfies $F$.

Let $\alpha$ satisfy $F$. Assume $\alpha\not\vDash C \lor x$, If $x\not\in Var(F)$ we can choose $\alpha(x) = \top$. 

By assumption, we have $\alpha(x) = \bot$. Let $\alpha'(x) = \top$ and $\alpha'(y) = \alpha(y)$ for $y \not= x$ and $y\in Var(F)$. Clearly $\alpha' \vDash C$, for every $C' \in F$ if $\overline x \not\in C'$, $\alpha' \vDash C'$ follows. If $\overline x \in C'$, then there exists another $y\in C\setminus \{x\}$ with $\overline y\in C'$, due to the definition of blocked. Since $\alpha(y) = \alpha'(y) = \bot, \alpha\vDash C'$ follows.


> Blocked clause elimination is [confluent](Confluence.md)

Each step of $\Pi_{BCE}$ removes a clause, no infinite sequence is possible. Let $C$ be blocked in $F$ on literal $x$. Thus, for every clause $(D\lor \overline x)$ in $F$, the resolvent $C\lor D$ is a tautology. Removing any other clause $E \not = (D\lor \overline x)$ can not create a new non tautological resolvent. Thus $C$ remains blocked in $F\setminus \{E\}$.

