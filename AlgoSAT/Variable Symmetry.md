let $\varphi: Var(F) \to Var(F)$ be a [bijection](Bijektiv.md) of [variables](Variable.md) over $F$. Note that we can trivially extend $\varphi$ to act on [literals](AlgoSAT/Literal.md), by defining $\varphi(\neg x) = \neg\varphi(x)$.

We call $\varphi$ a _variable [Symmetry](Symmetry.md)_ iff $F = F^\varphi$ holds.

