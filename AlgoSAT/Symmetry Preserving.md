

An operation $\Pi$ is isomorphism-invariant whenever it is invariant under renaming of literals.

For all $F$, all renamings of literals $\varphi$:
$$F \to^\Pi F' \implies \varphi(F) \to^\Pi \varphi(F')$$

If $\Pi$ is [confluent](Confluence.md) and isomorphism-invariant, it follows that the result that applies $\Pi$ exhaustively is symmetry-preserving:

Let $F \to^{\Pi*} F^*$. We want to show that this is symmetry preserving.
For every [Syntactic Symmetry](Syntactic%20Symmetry.md) $\varphi$ of $F$
$$F = \varphi(F) \to^\Pi\varphi(F_1)\to^\Pi \dots \to^\Pi \varphi(F^*)$$
Due to confluence, we know that $F^* = \varphi(F^*)$. Thus
$$\varphi|_{Lit(F^*)} \in Aut_{syn}(F^*)$$


