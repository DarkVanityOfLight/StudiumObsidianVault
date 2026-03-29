The following problems are polynomial time equivalent:

1. The [Graph Isomorphism](Graph%20Isomorphism.md) problem
2. The colored graph isomorphism problem
3. The [Graph Automorphism](Graph%20Automorphism.md) problem
4. The counting automorphism problem
5. The [Orbit](Orbit.md) problem

All of these problems are [Graph Isomorphism Complete](Graph%20Isomorphism%20Complete.md).

> Graph isomorphism and colored graph isomorphism are polynomial-time equivalent

Given uncolored [Graphs](AlgoSAT/Graph.md) $G_1, G_2$, we construct monochromatically colored graphs $G_1'$ and $G_2'$, where each vertex obtains color $0$.

Given vertex-colored graphs $G_1, G_2$, we construct uncolored graphs $f(G_1)$ and $f(G_2)$ such that $G_1 \cong G_2$ iff $f(G_1) \cong f(G_2)$, by appending binary counting gadgets.


> Graph isomorphism polynomial-time reduces to the orbit problem

Given graphs $G_1, G_2$, we decide $G_1 \cong G_2$ using an oracle to the orbit problem. Without loss of generality assume $V(G_1) \cap V(G_2) = \emptyset$. 
We insert universal nodes $v_1$ and $v_2$ into $G_1$ and $G_2$, which is a node connected to all vertices. Then create $G = G_1 \cup G_2$:
$$G_1 \cong G_2 \iff v_1 \in v_2^{Aut(G)}$$

> The orbit problem is polynomial-time reducible to the colored graph isomorphism problem

Construct an orbit partition of $G$ using a colored graph isomorphism oracle.

- We test whether $v, w\in V(G)$ are in the same orbit.
- Using the oracle, we check whether $G_v \cong G_w$. The result determines whether $v$ and $w$ are in the same orbit.
- By testing all possible pairs, we obtain the orbit partition



> The graph automorphism problem is polynomial time reducible to the graph isomorphism problem

We compute the orbits, if they have size $1$, then $Aut(G) = \{id\}$. Otherwise pick some orbit $O$ with $|O| > 1$ and $v \in O$. For each $v'\in O\setminus\{v\}$ compute $\varphi(v')\in Aut(G)$ with $\varphi_{v'}(v) = v'$ via an isomorphism between $G_v$ and $G_v'$. Recursively compute $\langle S\rangle = Aut(G_v)$ and return $S\cup\{\varphi_{v'} \in O\}$.

$$\langle S \cup \{\varphi_{v'} | v' \in O\}\rangle = Aut(G)$$

$\subseteq$ follows immediately, since $S$ and $\varphi_{v'}$ are automorphisms of $G$.
$\supseteq$ We set $\varphi_v = id$, for $\psi \in Aut(G)$, let $v' = \psi(v)$. Then $\psi = \varphi_{v'}\varphi^{-1}_{v'}\psi$, since $\varphi^{-1}_{v'}\psi$  is in $Aut(G_v) = \langle S \rangle$ since it maps $v$ to itself. $\varphi_{v'}$ is by definition in $\{\varphi_{v'} | v'\in O\}$. We can conclude that $\varphi \in \langle S\cup\{\varphi_{v'} | v'\in O\}\rangle$.
> The GI problem is polynomial time reducible to the Automorphism problem

Without loss of generality assume $V(G) \cap V(H) = \emptyset$, and assume $G$ and $H$ are connected, otherwise insert a universal node. Let $\langle S \rangle = Aut(G\cup H)$
$$G \cong H \iff \exists g\in S. g(V(G)) = g(V(H))$$

> The counting automorphism problem polynomial time reduces to the graph isomorphism problem

We follow the same reduction as with the Automorphism problem,
$$|Aut(G_v)| \cdot |O| = Aut(G_v)$$
From before we know we can write $\varphi\in Aut(G)$ as $\varphi = \varphi_w\psi$ where $w\in O$ and $\psi \in Aut(G_v)$.
It suffices to show $\varphi_w Aut(G_v) \cap \varphi_{w'}Aut(G_v) = \emptyset$ whenever $w\not= w'$. Suppose $\varphi_w\psi = \varphi_{w'}\psi'$. Then $\varphi_w\psi(v) = w$ and $\varphi_{w'}\psi'(v) = w'$. Thus $w = w'$

> The GI problem is polynomial time reducible to the counting Automorphism problem.

Without loss of generality assume $V(G) \cap V(H) = \emptyset$, and assume $G$ and $H$ are connected, otherwise insert a universal node.
$$|Aut(G\cup H)| = \begin{cases}
|Aut(G)| \cdot |Aut(H)| &\text{if } G\not\cong H\\
2\cdot |Aut(G)| \cdot |Aut(H)| &\text{if } G\cong H
\end{cases}$$

