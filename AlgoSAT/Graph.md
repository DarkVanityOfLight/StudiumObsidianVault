[Graph](Programmiersprachen/Graph.md) [Graph](Mathe/Graph.md)

A graph $G = (V, E)$ consists of a set of veritces $V$ and a set of edges $E \subseteq V \times V$. Unless stated otherwise, we assume that
- $V = \{0, \dots, n-1\}$
- $m = |E|$
- $E$ contains no self-loops, there is no $v\in V$ with $(v, v) \in E$ 
- $G$ is undirected, meaning $E$ is a symmetric relation

Given a graph $G = (V, E)$
- We call $v_1, v_2\in V$ _adjacent_ or _neighbors_, iff $(v_1, v_2)\in E$ or $(v_2, v_1)\in E$
- We call a vertex $v\in V$ _incident_ to an edge $(v_1, v_2) \in E$, whenever $v_1 = v$ or $v_2 = v$ holds.
- We denote with $N(v)$ for $v\in V$ all the neighbors of $v$
- We denote with $deg(v) = |N(v)|$ the degree of $v$, or the number of neighbors of $v$.



## Vertex colored Graphs
We often consider vertex-colored graphs.

Let $G = (V, E)$
- A _vertex coloring_ $\pi: V\to C$ is a map from vertices to an arbitrary set of colors $C$
- For computations, we assume $C\subseteq \{0, \dots, n-1\}$
- A vertex-colored graph $((V, E), \pi)$ is a graph together with a vertex coloring.

We call $\pi^{-1}(c)$ a color class. If $\pi^-1(c) = 1$ we call $c$ a singleton. If all vertices obtain a different color in $\pi$ we call $\pi$ discrete.

If $\pi: V\to C$ is a coloring and we have an ordering of the colors $C$, then we can associate $\pi$ with an ordered partitioning of the vertices. We refer with $P^\le_\pi$ to the ordered partitioning of vertices $C$ according to $\pi$ and $P_\pi$ the unordered one.

