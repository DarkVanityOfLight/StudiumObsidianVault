[Canonization](Canonization.md)
A _canonical form_ is a mapping $F$ such that for all [strings](String%20Isomorphism.md) $\tau_1, \tau_2$:
1. $F(\Gamma, \tau_1) \cong_\Gamma \tau_1$
2. if $\tau_1 \cong_\Gamma \tau_2$, then $F(\Gamma, \tau_1) = F(\Gamma, \tau_2)$

Given $\Gamma \le Sym(\Omega)$ as a generating set and $\tau\in\Sigma^\Omega$, we want to compute the canonical representative $F(\Gamma, \tau)$ for  a fixed canonical form $F$.


Let $G = (V, E)$ be an unordered [Graph](AlgoSAT/Graph.md). We define strings
$$\tau_G : \left(V \atop 2 \right) \to \{0, 1\} \text{ by } \tau_G(\{x, y\}) = \begin{cases}1 &\text{if } (x, y)\in E\\ 0 &\text{otherwise}\end{cases}$$
For any $\varphi\in Sym(V)$
$$\varphi(G) = G' \iff \varphi(\tau_G) = \tau_{G'} \text{ under } Sym(V)^{(2)}$$

So [Graph Isomorphism](Graph%20Isomorphism.md) reduces to string isomorphism under $Sym(V)^{(2)}$. Naturally, a string canonical form of $\tau_G$ under $Sym(V)^{()}$ yields a canonical form of $G$. Hence, graph canonization reduces to string canonization.


