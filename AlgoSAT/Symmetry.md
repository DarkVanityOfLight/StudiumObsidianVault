---
aliases:
---
[Symmetrie](Mathe/Symmetrie.md)

For a set $M$ and map $\varphi$ we define
$$\varphi(M) = \{\varphi(x) | x\in M\}$$
A bijection of [Literals](AlgoSAT/Literal.md) $\varphi: Lit(F) \to Lit(F)$ is a _syntactic symmetry_ iff
- $F =\varphi(F)$ and
- $\varphi(\overline x) = \overline{(\varphi(x))}$ hold.

> A symmetry maps the formula back to itself

