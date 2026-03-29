Given a graph $G = (V, E)$, the Mycielski graph $\mu(G)$ is obtained as follows:
- Include $G$ in $\mu(G)$
- For each $v\in V$ add a vertex $u\in U$ adjacent to all neighbors $N(v)$
- Add a vertex $w$ adjacent to all the new vertices in $U$.

If $G$ is triangle-free, so is $\mu(G)$.
The [Chromatic Number](Chromatic%20Number.md) $\chi(\mu(G)) = \chi(G) + 1$

