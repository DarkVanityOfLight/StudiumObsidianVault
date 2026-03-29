One iteration of color refinement maps every colored [Graph](AlgoSAT/Graph.md) $G = (V, E, \pi)$ to the colored graph $(V, E,\pi^r)$ given by:
$$\pi^r(v) = (\pi(v), \{\{\pi(v') | v' \in N(v)\}\})$$

Color refinement is [isomorphism](Graph%20Isomorphism.md)-invariant. For every [bijection](Bijektiv.md) $\varphi: V(G) \to V'$ we have
$$(V^\varphi, E^\varphi, (\pi^r)^\varphi) = (V^\varphi, E^\varphi, (\pi^\varphi)^r)$$

It does not depend on the names of vertices. Vertices of the same orbit _must_ obtain the same color under color refinement

$$(V, E, \pi) \cong(V', E', \pi') \iff (V, E, \pi^r) \cong (V', E', \pi'^r)$$

Iterating the refinement until fixpoint, the _stable coloring_ is the smallest $i$ such that $\pi^r_i = \pi^r_{i+1}$. We denote $R(G)$ the graph $G$ colored with its stable coloring.

Instead of refining everything at once, we refine a color class $C$ with respect to another class $R$.

We only consider edges between $C$ and $R$. We partition $C$ by the number of neighbors in $R$ and continue the refinements w.r.t new classes.

