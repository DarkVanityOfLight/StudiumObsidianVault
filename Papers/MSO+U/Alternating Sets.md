---
aliases:
  - alternating sets
---

> [!PDF|red] [MSO+U, p.5](MSO+U.pdf#page=5&selection=232,5,249,16&color=red)
> > Two sets $X$, $Y$ of depth-1 nodes alternating if every two nodes in $X$ are separated by a node in $Y$ , and vice versa
> 

$$
AltD(X, Y) := \forall x, x' (X(x) \land X(x') \to \exists y (Y(y) \land x < y < x'))
$$
"every two nodes in $X$ are separated by at least one node from $Y$"

$$Alt(X, Y) := AltD(X, Y) \land AltD(Y, X)$$
>[!QUESTION]
> Uniqueness $x\in X\to x \not \in Y$

