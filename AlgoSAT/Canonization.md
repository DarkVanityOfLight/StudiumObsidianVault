-Imagine this: A chemist wants to store a database of [molecule](Molekül.md) that are given as [graphs](AlgoSAT/Graph.md). Given a molecule, they want to know whether it is a new, unknown molecule. Only if it is new, should it be added to the database.


_Canonical_ forms provide a standard copy for a graph.

> A canonical form $Can: G \to G$ maps graphs to graphs with
> 1. $V(Can(G)) = \{0,\dots, n-1\}$
> 2. $Can(G) \cong G$
> 3. $H\cong G \implies Can(G) = Can(G)$

The image of $G$ under the canonical form is called the _canon_ of $G$.


The [Graph Isomorphism](Graph%20Isomorphism.md) problem reduces to equality testing of the canon. The converse is open.

A _canonical labeling_ assigns to every graph $G$ an isomorphism $X_G$ from $G$ to the canon of $G$.

![all_slides_handout_experimental, p.10](all_slides_handout_experimental.pdf#page=595&rect=31,84,314,212)

## Lex-leader
Let $Enc(G)$ denote the encoding of $G$ as an adjacency matrix. We define $Can(G)$ to be the graph $G'$ for which the adjacency matrix $Enc(G')$ is lexicographical minimal among all $G'\cong G$.

