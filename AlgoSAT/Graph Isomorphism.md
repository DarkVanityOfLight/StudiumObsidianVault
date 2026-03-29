---
aliases:
  - graph isomorphism problem
---
[Isomorphism](Automata/Isomorphism.md) [Isomorphismen](Isomorphismen.md)

A [bijection](Bijektiv.md) of vertices $\varphi: V_1 \to V_2$ is an _isomorphism_ between [graphs](AlgoSAT/Graph.md) $G_1, G_2$, whenever $G_1^\varphi = (V_1^\varphi, E_1^\varphi) = (V_2, E_2) = G_2$ 

IF $\varphi$ is an isomorphism between $G_1$ and $G_2$, then $(v_1, v_2)\in E(G_1)$ holds iff $(v_1^\varphi, v_2^\varphi)\in E(G_2)$ holds.

The isomorphism maps edges to edges and non-edges to non-edges. Forgetting the names of vertices, the isomorphic graphs are identical or indistinguishable.

Two graphs are said to be _isomorphic_, if there is an isomorphism between them, written $G_1 \cong G_2$.

Given two graphs $G_1$ and $G_2$ we want to decide whether $G_1$ and $G_2$ are isomorphic.


> Let $G_1 = (V_1, E_1)$ and $G_2 = (V_2, E_2)$ be two graphs. Let $\varphi: V_1 \to V_2$ denote a bijection between the vertices. The following statements are equivalent:
> - $G_1^\varphi = G_2^\varphi$
> - $(v, w)\in E_1$ iff $(v^\varphi, w^\varphi)\in E_2$
> - For every $v\in G_1$, it holds that $N_{G_2}(v^\varphi) = (N_{G_1}(v))^\varphi$


The graph isomorphism problem can be solved in quasi-polynomial time, but the algorithms are not used in practice.

The relation $\cong$ of being isomorphic is an [equivalence relation ](Äquivalenzrelationen.md) between graphs.

- for every graph $G$ $G \cong_{id} G$ holds
- if $G_1 \cong_\varphi G_2$ then $G_2 \cong_{\varphi^{-1}} G_2$ 
- if $G_1 \cong_{\varphi_1} G_2 \cong_{\varphi_2} G_3$ then $G_1 \cong_{\varphi_2 \circ \varphi_1} G_3$

The _isomorphism type_ or _isomorphism class_ of $G$ is the set of all graphs isomorphic to $G$.

## Colored Graph Isomorphism

We define isomorphisms over _vertex-colored graphs_.
Let $G_1 = (V_1, E_1, \pi_1)$ and $G_2 = (V_2, E_2, \pi_2)$ be two vertex-colored graphs. Let $\varphi: V(G_1) \to V(G_2)$ denote a bijection between the vertices.

We call $\varphi$ an isomorphism between the two vertex-colored graphs if
1. $G_1^\varphi = G_2$ holds and
2. for all $v\in G_1$ it holds that $\pi(v) = \pi(v^\varphi)$




