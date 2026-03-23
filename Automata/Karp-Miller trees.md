Karp-Miller trees are used to find an [Ideal Decomposition](Ideal%20Decomposition.md) of the [Coverability Set](Coverability%20Set.md) 
$$Cover(\mathcal V)$$
for the [VASS](Vector%20Addition%20Systems.md) $\mathcal V = (Q, T, q_0)$. From this we obtain a second algorithm for the [Coverability Problem](Coverability%20Problem.md) in VASS.

We will use $\omega$-arithmetic in the trees, for $n\in\mathbb N$
$$\omega + n := \omega \qquad \omega - n := \omega$$

A Karp-Miller Tree is a [[Tree]] with:
- Nodes labeled in $Q\times \mathbb N^d_\omega$
- Edge Labels in $T$
- Additional _upward edges_ pointing from nodes to ancestors


> Let the label of node $v$ be $\gamma_v$. We call $v$ complete if $v$ has an outgoing $\tau$-edge for each $\tau\in T$ activated in $\gamma_v$.

> Suppose $\gamma = (q,\mathbf u), \gamma' = (q, \mathbf u') \in Q\times\mathbb N^d_\omega$ with $\mathbf{u} \le \mathbf{u'}$
> Then $\Omega(\gamma, \gamma') := (q, \mathbf v)$ with: $$\mathbf v(i) := \begin{cases}\mathbf u(i) & \text{if } \mathbf u(i) = \mathbf u'(i) \\ \omega & \text{if } \mathbf{u}(i) < \mathbf u'(i)\end{cases} \text{for } i\in\{1, \dots, d\}$$

The following algorithm constructs a Karp-Miller Tree
```
Input: VASS V = (Q, T, q0)

t := tree with a single node
label(root(t)) := (q0, 0)

while there exists an incomplete leaf v in t do
    for each transition tau in T that is activated in gamma_v do
        compute gamma such that
            gamma_v --tau--> gamma
            where gamma is in Q x N^d_omega

        if there exists an ancestor v_bar of v with gamma_v_bar <= gamma then
            choose such v_bar with maximal distance from the root

            if gamma_v_bar = gamma then
                add an upward edge from v to v_bar labeled tau

            else if gamma_v_bar < gamma then
                gamma_new := Omega(gamma_v_bar, gamma)
                create child v' of v
                label(v') := gamma_new
                label edge (v, v') with tau

        else
            create child v' of v
            label(v') := gamma
            label edge (v, v') with tau
```

The Karp Miller tree is finite, and its construction terminates:

Suppose the algorithm does not terminate, then the constructed tree is infinite. It is finitely branching so by [Koenigs Lemma](Koenigs%20Lemma.md), there is an infinite branch. Let $(q_1, \mathbf u_1), (q_2, \mathbf u_2), \dots \in Q\times\mathbb N^d_\omega$ be the labels on the branch. Since $\le$ is a [WQO](Well-quasi-ordering.md) there is an ascending subsequence $(q'_1, \mathbf u_1') \le (q'_2, \mathbf u_2' \le \dots)$.
The branch cannot contain a label twice, otherwise, we would have introduced an upward edge, hence $(q_1', \mathbf u_1') < (q_2', \mathbf u'_2) < \dots$. This means the algorithm introduces an $\omega$ when it adds $(q_i', \mathbf{u}_i')$, for every $i \in\mathbb N, i\ge 2$. Along the branch, the set of $\omega$ coordinates can never get smaller, thus we can introduce an $\omega$ at most $d$ times in a branch, which is a contradiction.

## Karp-Miller graph
The Karp Miller graph is obtained from the tree by "materialising" upward edges. 

> For $\mathbf u\in\mathbb N^d_\omega$ and $k\in\mathbb N$, let $\mathbf u^{(k)} \in\mathbb N^d$ denote the vector obtained by replacing each $\omega$ by $k$.

For every node labeled $(q, \mathbf u) \in Q\times \mathbb N^d_\omega$ in the Karp-Miller graph and every $k\in\mathbb N$, there is a reachable configuration $(q, \mathbf v)\in Q\times\mathbf N^d$ in the VASS with $(q, \mathbf u^{(k)}) \le (q, \mathbf v)$.

It suffices to show the proposition for the Karp-Miller tree.

We proceed by induction on the distance from the root.
Let $v$ be a node in the Karp-Miller tree.

1. If $v$ was added without introducing $\omega$ we apply induction to its parent node
2. If $v$ was added with introduction of $\omega$ let $\overline v$ be the ancestor used to construct $v$, let $(q, \mathbf{\overline u})$ and $(q, \mathbf u)$ be the labels of $\overline v$ and $v$. Consider the transition sequence $\sigma = \tau_1 \dots \tau_m$ on the branch from $\overline v$ to $v$. In thos components where $\sigma$ has negative effect $\mathbf{\overline u}$ must have $\omega$. In every new $\omega$-component, $\sigma$ must have a positive effect. By induction hypothesis, for each number $\ell\in\mathbb N$ there is a $\mathbf y\in\mathbb N^d$ with $(q_0, \mathbf 0) \to^* (q,\mathbf y) \ge (q, \mathbf{\overline u}^{(\ell)})$. Then there is a (large) $\ell\in\mathbb N$ and $\mathbf y, \mathbf u'\in\mathbb N^d$ such that $(q_0, \mathbf 0) \to^* (q, \mathbf y) \ge (q, \mathbf{\overline u}^{(\ell)})$ and $(q, \mathbf{\overline u}^{(\ell)}) \to^{\sigma^k} (q, \mathbf u') \ge (q, \mathbf u^{(k)})$. Since VASS are [WSTS](Well-structured%20transition%20systems.md) there is also $\mathbf u'' \in\mathbb N^d$ with $(q_0, \mathbf 0)\to^* (q, \mathbf y) \to^{\sigma^k} (q, \mathbf u'')$ and $\mathbf u'' \ge \mathbf u' \ge \mathbf u^{(k)}$.



> For every run 
> $$(q_0, \mathbf u_0) \to (q_1, \mathbf u_1) \to \dots \to (q_m, \mathbf u_m)$$ in $\mathcal V$, there is a path 
> $$(q_0, \mathbf u_0') \to (q_1, \mathbf u_1') \to \dots \to (q_m, \mathbf u_m')$$
> in the Karp-Miller graph such that $(q_i, \mathbf u_i) \le (q_i, \mathbf u_i')$ for every $i\in\{1, \dots, m\}$.
 (By induction on $m$)


These two propositions imply

Let $(q_1, \mathbf v_1), \dots, (q_n,\mathbf v_n) \in Q\times \mathbb N^d_\omega$ be the labels of the nodes in the Karp-Miller graph. Then
$$Cover(\mathcal V) = \{q_1\}\times Idl(\mathbf v_1) \cup \dots \cup \{q_n\} \times Idl(\mathbf v_n)$$
In particular, given a VASS, one can effectively compute the [ideal](Ideal.md) decomposition of its coverability set.


