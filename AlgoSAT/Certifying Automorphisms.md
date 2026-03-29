We want to [verify](Certifying%20Algorithms.md) that a given permutation $\varphi$ is an [automorphism](Graph%20Automorphism.md) of a given graph $G$.

We can check that:
- $E(G)^\varphi = E(g)$
- $N(v)^\varphi = N(v^\varphi)$ for each $v\in support(\varphi)$

In the case that $|support(\varphi)|\ll |V(G)|$ the above is too expensive.
Instead we only check vertices in the support of $\varphi$
$$N(v)^\varphi = N(v^\varphi) \text{ for each } v\in support(\varphi)$$

