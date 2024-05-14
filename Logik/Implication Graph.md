

An implication graph corresponding to a trail $T = (l_1, t_i),\dots, (l_m, t_m)$ is a directed acyclic graph $G = (V, E)$ with:

1. Each $v\in V$ is of the form $l_i @ l_T(l_i)$ or $\bot$
2. $l_i@k \to_E l_j @k'$ if $k \leq k', t_j = d$ and there is a clause $C$ containing $\neg l_i$ which was used to deduce $l_j$ in $T$. We will label this edge by $C$ to emphasize this fact.

A conflict graph is a subgraph of an implication graph containing $\bot$ and all vertices leading to $\bot$.


## Example

$$ \lbrace \neg x_1, \neg x_5, \neg x_6 \rbrace \lbrace \neg x_1, \neg x_5, x_6 \rbrace\lbrace \neg x_2, x_3\rbrace \lbrace \neg x_3, x_4 \rbrace\lbrace x_5, x_7 \rbrace\lbrace x_5, \neg x_7 \rbrace$$

$$T = [(x_1, g)(x_2, g)(x_3, d)(x_4, d)(x_5, g)(\neg x_6, d)]$$

![](Implication%20Graph%202024-05-01%2012.47.17.excalidraw.md)

## Cutting

Given a conflict graph $G = (V, E)$, a cut of $G$ is a partition of $V$ into two parts $V_1$(reason side) and $V_2$ conflict side such that:
1. $V_1$ contains all vertices without incoming edges
2. $V_2$ contains $\bot$ and at least on [literal](Literal.md) $l$ such that $l\to_E \bot$
