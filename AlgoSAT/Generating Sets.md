Since we are interested in all [symmetries](Graph%20Automorphism.md) $Aut(G)$ of a [Graph](AlgoSAT/Graph.md) $G$, and there might be a lot of automorphisms it is infeasible to store all of $Aut(G)$.

Instead we can observe the following, when $\varphi\in Aut(G)$ and $\varphi'\in Aut(G)$, so is $\varphi \circ \varphi'\in Aut(G)$

$$G^{\varphi \circ \varphi'} = (G^{\varphi'})^\varphi = G^\varphi = G$$

So instead we don't store all symmetries, but only a few that produce all others.

A [set](Mengen.md) of symmetries $S\subseteq Aut(G)$ is called a generating set for $Aut(G)$, if every symmetry can be written as a composition of elements of $S$. We write $\langle S\rangle = Aut(G)$.

