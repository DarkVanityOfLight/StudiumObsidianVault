---
aliases:
  - confluent
---

Let $\Pi$ be a (possibly non-deterministic) transformation on [formulas](Formula.md). For a formula $F$, let
$$\Pi(F) = \{F_1, \dots, F_m\}.$$
We write 
$$F \to^\Pi F' \text{ whenever } F'\in\Pi(F).$$

Exhaustive application is written
$$F \to^{\Pi*} F^*, \text{ meaning that } \Pi(F^*) = \emptyset$$

A transformation $\Pi$ is terminating if any sequence starting from $F$ reaches a formula $F^*$ with $\Pi(F^*) = \emptyset$.

A terminating transformation $\Pi$ is _confluent_ if for every formula $F$ the following holds: If $F \to^{\Pi*} F_1^*$ and $F \to^{\Pi*} F_2^*$, then $F_1^* = F_2^*$. 

