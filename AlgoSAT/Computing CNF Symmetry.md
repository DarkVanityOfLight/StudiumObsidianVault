We want to compute all [Symmetries](Symmetry.md) of a given CNF [Formula](Formula.md) $F$. 

> [!Model Graph for CNF]
> We call a [Graph](AlgoSAT/Graph.md) $G(F)$ a _model graph_ for a CNF formula $F$, iff
> 1. $Lit(F) \subseteq V(G(F))$
> 2. $Aut(G(F))|_{Lit(F)} = Aut(F)$

We encode a given CNF $F$ as a vertex-colored graph $G = M(F)$.

$$V(G) = Lit(F) \cup F$$
There is a vertex for each [Literal](AlgoSAT/Literal.md) and for each [Clause](Clause.md) in $F$.

$$E(G) = \{\{v, \neg v\} | v\in Var(F)\} \cup \{\{l, C\} | C\in F \land l\in C\}$$
There is an edge connecting, each literal $l$ to its negated literal $\neg l$ and each clause $C$ to all literals $l\in C$. For $\pi(G)$, we color literals with color $0$ and clauses with color $1$.

> $M(F)$ is a model graph of $F$

Every symmetry $\varphi$ of $M(F)$ can be restricted to a symmetry $\varphi|_{Lit(F)}$ of $F$. The colors ensure that literals go to literals and clauses to clauses. For a literal $x$, let $\varphi(x) = x'$. Since $\neg x$ is the only $0$ colored neighbor of $x$, $\varphi(\neg x) = \neg x'$ follows. Hence, $\varphi$ respects negation. Finally for each $C\in F, \varphi(C)\in F$, from the fact that $C$ connects to all its contained literals, meaning there is a clause vertex $\varphi(C)$ that connects to all of its literals $\varphi(l), l\in C$.

Conversely, every symmetry $\varphi$ of $F$ extends to a symmetry of $M(F)$. We extend $\varphi$ to $M(F)$ by mapping each $C$ to $\varphi(C)$, by construction, our extension respects the colors of $M(F)$. Since $\varphi$ respects negation, for each variable $x$ the edge $\{x, \neg x\}$ is preserved. For each edge $\{l, C\}$ observe that if $\varphi(l) = l'$, then $l'\in\varphi(C)$. Hence there is an edge $\{\varphi(l), \varphi(C)\}$.


