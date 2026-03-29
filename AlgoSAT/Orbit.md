Let $G$ be a [Graph](AlgoSAT/Graph.md) and $v\in V(G)$. The _orbit_ of $v$, denoted by $v^{Aut(G)}$, is the set of images of $v$ under all [automorphisms](Graph%20Automorphism.md) of $G$. Formally
$$v^{Aut(G)} := \{u\in V(G) | \exists \varphi\in Aut(G) | \varphi(v) = u \}$$

The relation "$u$ is in the orbit of $v$" is an [equivalence relation](Äquivalenzrelationen.md). The equivalence classes are called the _orbits_ of $Aut(G)$ and form the _orbit partition_ $Orb(G)$.

The orbit partition _does not_ uniquely determine the automorphism group.


Using [Generating Sets](Generating%20Sets.md) we can compute the Orbits.
Given a generating set $S$ with $\langle S \rangle = Aut(G)$ we want to compute the orbit partition $Orb(G)$ using $S$.

We initialize a union find data structure over $n$.
Then For each $\varphi\in S$ and each $v\in support(\varphi)$ we do $union(v, \varphi(v))$.

Given a colored graph $G = (V, E, \pi)$. All color classes of $G$ are unions of orbits.

If $v\in w^{Aut(G)}$ holds, then $\pi(v) = \pi(w)$ must hold by definition.
In other words, if $\pi(v) \not= \pi(w)$, then $v$ and $w$ can not be in the same orbit.

