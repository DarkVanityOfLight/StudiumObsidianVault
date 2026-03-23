Let $V = (Q, T, q_0)$ be a [VASS](Vector%20Addition%20Systems.md). Is there an infinite run in $V$ such that $q$ is visited infinitely often ([Recurrent State Reachability](Recurrent%20State%20Reachability.md))

A run 
$$(q_0, \mathbf u_0) \to (q_1, \mathbf u_1)\to\dots\to(q_n, \mathbf u_n)$$
is self-covereing on $q$ if there exists $i < n$ such that $q_i = q_n = q$ and $\mathbf u_i \le \mathbf u_n$

> There is a run in $V$ that visits $q\in Q$ infinitely often iff $V$ has a self-covering run on $q$.

If a run visits $q$ infinitely often, then there exists $i< j$ such that $q_i = q_j = q$ and $\mathbf u_i \le \mathbf u_j$.

Suppose that $(q_0, \mathbf 0)\to^*(q, \mathbf u) \to^+ (q, \mathbf u + \mathbf v)$ for some $\mathbf u, \mathbf v\in\mathbb N^d$, where $\to^+$ is the transitive closure of $\to$. By compatibility of $\le$ we can construct the run
$$(q_0, \mathbf 0) \to^* (q, \mathbf u)\to^+ (q, \mathbf u+\mathbf v) \to^+ (q, \mathbf u + 2\mathbf v) \to^+ \dots$$
that visits $q$ infinitely often.


Recall the ![Karp-Miller graph](Karp-Miller%20trees.md#Karp-Miller%20graph)
A path $v_0 \to^{\tau_1} v_1 \to^{\tau_2} \to \dots \to^{\tau_n} v_n$ is a cycle if $n \ge 1$ and $v_0 = v_n$. It is a $q$-cycle if $\gamma_{v_i} = (q, \mathbf u)$ for some $0 \le i\le n$ and some $\mathbf u$. Its effect is $\sum^n_{i=1} \mathbf v_i$ where $\tau_i = (q_{i-1}, \mathbf v_i, q_i)$ for all $1 \le i \le n$.

> There is a self-covering run on $q\in Q$ iff the Karp-Miller graph of $V$ contains a $q$-cycle with nonnegative effect.

Since $V$ has a self-covering run on $q$ there exists a run of the form
$$(q_0, \mathbf 0) \to^* (q, \mathbf u) \to^+ (q, \mathbf u + \mathbf v) \to^+ (q, \mathbf u + 2\mathbf v) \to^+ \dots$$
in $V$ for some $\mathbf v\in\mathbb N^d$. Then there exists a path
$$(q_0, \mathbf 0) \to^* (q, \mathbf u_0) \to^+ (q, \mathbf u_1) \to^+ (q, \mathbf u_2) \to^+ \dots$$
in the Karp Miller graph such that $\mathbf u + k\mathbf v \le \mathbf u_k$ for all $k\in\mathbb N$. Since the Karp-Miller graph is finite there exists $i< j$ such that $\mathbf u_i = \mathbf u_j$. Then $(q, \mathbf u_i) \to^* (q, \mathbf u_j)$ is the desired $q$-cycle with effect $(j-1)\mathbf v\in\mathbb N^d$.


Consider a cycle $(q, \mathbf u)\to^{\tau_1} \dots \to^{\tau_n} (q, \mathbf u)$ where $\tau_i$ has effect $\mathbf v_i$ and $\mathbf v := \sum^n_{i=1} \mathbf v_i \ge \mathbf 0$. If we set $m = n\cdot \max\{||\mathbf v_i||: 1 \le i\le n\}$ then $\sum^k_{i=1} \mathbf v_i \ge (-m, \dots, -m)$ for all $1 \le k\le n$. By the property of the Karp-Miller graph there exists a reachable configuration $(q, \mathbf u')$ in $V$ where $\mathbf u' \ge \mathbf u^{(m)}$. Then $\mathbf u' +\sum^k_{i=1} \mathbf v_i \ge \mathbf 0$ for all $1 \le k\le n$ and
$$(q_0, \mathbf 0) \to^* (q, \mathbf u') \to^{\tau_1} \dots \to^{\tau_n} (q, \mathbf u' + \mathbf v)$$
is indeed a self-covering run on $V$.


> The recurrent state reachability problem for VASS is decidable.

We view the Karp-Miller graph of the given $d$-VASS $V$ as a $\mathbb Z$-VASS $V_{KM}$:
- The states of $V_{KM}$ are the nodes in the graph
- Its transitions are labels of the edges in the graph.
We need to test whether there is a run from $(q,\mathbf 0)$ to $(q, \mathbf u)$ of length $\ge 1$ where $\mathbf u\in\mathbb N^d$. We proved that the reachability set of a $\mathbb Z$-VASS is effectively Presburger definable. By a simple modification of the proof one can show that $\{\mathbf u \in\mathbb Z^d | (q, \mathbf 0) \to^+ (q,\mathbf u)\}$ is effectively Presburger definable by a formula $\varphi(\mathbf x)$.
Finally we test wheter $\exists \mathbf x(\mathbf x \ge \mathbf 0 \land \varphi(\mathbf x))$ is true.


