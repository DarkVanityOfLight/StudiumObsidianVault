For a [Graph](AlgoSAT/Graph.md) $G$ with stable coloring $\pi$ the _quotient graph_ $Q(G, \pi)$ is a vertex and edge labeled graph with

- $V(Q(G, \pi)) := \pi(V(G))$
- $E(Q(G, \pi)) := \{(C, C') | C, C' \in \pi(V(G))\}$
- $l_v(Q(G, \pi))(c) := |\pi^{-1}(c)|$
- $l_E(Q(G, \pi))((c_1, c_2)) := d_{\pi^-1(c_2)}(v)$ where $v\in\pi^{-1}(c_1)$ is arbitrary
The quotient graph is a graph invariant, even when we hash colors.

