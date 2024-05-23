

## Decision Level

Given a trail $T = (l_1, t_i), \dots, (l_m, t_m)$, define the decision level of $l_i$ $l_T(l_i)$ by induction as:

1. $l_T(l_0) = 0$  (assume an imaginary literl $l_0$)
2. for each $i\in\lbrace  1, \dots, n\rbrace$, define $l_T(l_i) = l_T(l_{i-1})$ if $t_i = d$, and $l_T(l_i) = l_T(l_i-1) + 1$ if $t_i = g$

Thus there exists at most one guessed literal at any decision level.



## Learning a conflict clause

Given a cut $V_1, V_2$ of a [conflict graph](Implication%20Graph.md) $G = (V, E)$ the conflict clause associated with this cut is
$$\lbrace\neg l: \exists k\in\mathbb N, l@k\in V_1 \cap\text{pred}(V_2)\rbrace$$
where $\text{pred}(V_2) := \lbrace v\in V_1 : \exists w\in V_2 (v\to_E w) \rbrace$

![conflictgraph.excalidraw](conflictgraph.excalidraw.md)

here the conflict clause would be $\lbrace \neg x_5, \neg x_1\rbrace$


## Learning without Implication Graphs

The construction of the fill implication graph is mostly not needed, we perform a backward resolution to identify the learned clause, and where to backjump to. The backward resolution corresponds to constructing a partial implication graph.

### Backward Resolution

From a [Trail](Trails.md) $T$ that is leading to a conflict clause $C$, the idea is to  construct the partial conflict graph $\bot$ backwards!

The following algorithm is sometimes called backward resolution:

```python
C = conflict_associated_with_T
while C contains > 1 literals at current level:
	(l, d, C_prime) = pop(T)
	C = Resolve(C, C_prime, l)
phi = phi union {C}
Backjump C
```

