Let $F_\ell$ denote all [clauses](Clause.md) of $F$ containing [Literal](AlgoSAT/Literal.md) $\ell$.

> [!Resolution on variable]
> Given two clauses $C = (x \lor p_1 \lor \dots\lor p_i)$ and $D = (\neg x \lor q_1 \lor \dots \lor q_j)$, the _resolvent_ of $C$ and $D$ on variable $x$ ($C \bowtie_x D$) is $(p_1 \lor \dots \lor p_i \lor q_1 \lor \dots\lor q_j)$
> [Resolution](AlgoSAT/Resolution.md) on clause sets $F_x$ and $F_{\neg x}$ ($F_x \bowtie_x F_{\neg x}$) generates all non-tautological resolvents of $C \in F_x$ and $D\in F_{\neg x}$

Given a CNF [Formula](Formula.md) $F$, variable elimination (or DP resolution) removes a variable $x$ by replacing $F_x$ and $F_{\neg x}$ by $F_x \bowtie_x F_{\neg x}$.

Variable is a complete proof procedure. Applying VE until fixpoint results in either the empty formula or the empty clause.


Variable elimination preserves [Equisatisfiability](Equisatisfiable.md).

$\implies$ If $\alpha\vDash F$, then the resolvents $A_i \lor B_j$ follow by resolution from $x \lor A_i$ and $\neg x \lor B_j$. Removing $x$ clauses from $F$ doesn't destroy satisfiability. Hence $\alpha|_{Var(F)\setminus\{x\}} \vDash DP_x(F)$.

$\impliedby$ Assume $\alpha'$ over $Var(F) \setminus \{ x \}$ satisfies all resolvents $A_i \lor B_j$ and all clauses in $F_0$, we can extend the assignment to $x$
- If some $A_i$ is false under $\tau'$, then every $B_j$ must be true. Set $x := \tau$. Then each $(x \lor A_i)$ is true and each $(\neg x \lor B_j)$ becomes $B_j$, hence true.
- Otherwise all $A_i$ are true. Set $x := \bot$. Then $(x \lor A_i)$ becomes $A_i$ and each $(\neg x \lor B_j)$ is true since $\neg x$ is true.

## Variable elimination by substitution

There are some more efficient opportunities for VE.

The general idea is to detect gates in the formula and use them to reduce the number of added clauses.

