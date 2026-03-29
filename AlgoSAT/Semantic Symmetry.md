Consider a [bijection](Bijektiv.md) $\varphi: Lit(F) \to Lit(F)$. We define the notion of a _semantic [Symmetrie](AlgoSAT/Symmetrie.md)_ $\varphi$ as follows:

1. For all complete [assignments](Assignment.md) $\tau$ of $F$ it holds that $$F[\tau] = \varphi(F)[\tau]$$
2. For all $\ell\in Lit(F)$ it holds that $\overline{\varphi(\ell)} = \varphi(\overline \ell)$

Every [Syntactic Symmetry](Syntactic%20Symmetry.md) of $F$ is also a _semantic_ symmetry of $F$.
The semantic symmetries of $F$ are a permutation group and computing the semantic symmetries is NP-hard.

We can apply semantic symmetries $\varphi$ on a complete assignment $\tau$ on $F$:
$$\varphi(\tau)(v) := \tau(\varphi(v))$$
$F$ evaluates to the same truth value under $\tau$ and $\varphi(\tau)$ 
$$F(\tau) = \varphi(F)[\varphi(\tau)] = F[\varphi(\tau)]$$

