Given a [Graph](AlgoSAT/Graph.md) $G$, a vertex color $\pi$ of $G$, a sequence of vertices $v\in V^*$, a refinment $Ref$ satisfies
1. $Ref(G^\varphi, \pi^\varphi, v^\varphi) = Ref(G, \pi, v)^\varphi$ holds for all $\varphi\in S_n$
2. Refines $\pi$, i.e., $Ref(G, \pi, v) \preceq \pi$ 
3. $\{v\}$ is a singleton cell in $Ref(G, v)$ for all $v\in v$.

If $\varphi\in Aut(G, \pi)$
$$Ref(G, \pi, v^\varphi) = Ref(G^\varphi, \pi^\varphi, v^\varphi) = Ref(G, \pi, v)^\varphi$$

## Cell Selector
Given a graph $G$ and vertex coloring $\pi$, the cell selector $Sel$ returns $' \subseteq V(G)$ satisfying
1. $Sel(G^\varphi, \pi^\varphi) = Sel(G, \pi)^\varphi$ for all $\varphi\in S_n$
2. $\pi$ is discrete iff $Sel(G, \pi) = \emptyset$
3. if $\pi$ is not discrete, $|Sel(G, \pi)| > 1$ and $Sel(G, \pi)$ is a color class of $\pi$

## Tree
Each node of the IR tree $T_{(Ref, Sel)}(G, \pi)$ corresponds to the sequence of vertices individualized in that node
1. The root of $T_{(Ref, Sel)}(G, \pi)$ is the empty sequence $\varepsilon$
2. If $v$ is a node in $T_{(Ref, Sel)}(G, \pi)$ and $C = Sel(G, Ref(G, \pi, v))$ then its children are $\{vv|v\in C\}$

---

For a vertex colored graph $(G,\pi)$ and $\varphi\in S_n$ we have
$$T(G, \pi)^\varphi = T(G^\varphi, \pi^\varphi)$$

If $v$ is a node of $T(G, \pi$) and $\varphi\in Aut(G, \pi)$, then $v^\varphi$ is a node of 
$T(G, \pi)$ and $T(G, \pi, v)^\varphi = T(G, \pi, v^\varphi)$

Leaves within a tree enocde [Automorphisms](Graph%20Automorphism.md) of the graph, leaves between two IR trees encode potential [isomorphisms](Graph%20Isomorphism.md) between two graphs.


## Finding Automorphisms
Fix one leaf of the tree, compare it to all other leaves of the tree, produce the candidate isomorphism between the discretely colored graphs at leaves and check if it actually is an isomorphism, if so we have found an automorphism

We can do the following improvement:
Assume we've already found some automorphism $S$, if we already explored $v$, we can cut away all nodes $v'$ with $v' = \varphi(v)$ for $\varphi\in \langle S\langle$.

> Intuitively: In $v'$ we will only find automorphisms already in $\langle S\rangle$

## Finding Isomorphisms
Consider IR trees $T_1, T_2$ for both input graphs.
Fix one leaf tree in $T_1$, compare it to all leaves in $T_2$, produce the candidate isomorphism between the discretely colored graphs at leaves and check if it actually is an isomorphism. If all leaves fail, the graphs are non-isomorphic.

