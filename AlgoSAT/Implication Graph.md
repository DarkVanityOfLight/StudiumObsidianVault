We define the implication graph at [decision level](CDCL%20-%20Conflict%20Driven%20Clause%20Learning.md#Decision%20Levels) $d$ $G_d = (V, E)$ as follows:
- $V$ contains one node for every decision literal assigned in the trail
- For each [literal](AlgoSAT/Literal.md) $\ell$ not yet in $G$ with [clause](Clause.md) $C = (\ell \lor \neg a_1 \lor \dots \lor \neg a_k)$ if $\neg a_1, \dots, \neg a_k$ already appear in the graph, add directed edges $a_i \to \ell$ for all $i\in[1, \dots, k]$

A variable is a _conflict variable_ if it occurs positively and negatively, we add a special node $\bot$, for every conflict variable $x$, connect $x$ and $\neg x$ to $\bot$. $G$ contains a conflict iff it contains a conflict variable.

