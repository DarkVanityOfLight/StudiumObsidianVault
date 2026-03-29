A [bijection](Bijektiv.md) of [literals](AlgoSAT/Literal.md) $\varphi: Lit(F) \to Lit(F)$ is a _syntactic [symmetrie](AlgoSAT/Symmetrie.md)_ iff
- $F = \varphi(F)$
- $\varphi(\neg x) = \neg\varphi(x)$ hold.
This allows us to exchange $x$ with $\neg x$. This is often called a _value symmetry_.

