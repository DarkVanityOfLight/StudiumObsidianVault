Let $\mathbf c = (c_0, \dots, c_n)$ be a sequence of natural numbers. We say that a pair $(i, j)$ with $i+1 < j$ is a _reversal_ in $\mathbf c$ if $c_i < c_{i+1} = \dots = c_{j-1} > c_j$ or $c_i > c_{i+1}$ or $c_i > c_{i+1} = \dots = c_{j-1} < c_j$.

If $\mathbf c$ has $r$ reversals then it can be divided into $r+1$ _phases_, there exist $0 = i+0 < i_1 < \dots < i_{r+1} = n$ such that $(c_{i_j}, \dots, c_{i_{j+1}})$ is ascending or descending for all $0 \le j\le r$.
A sequence of vectors
$$(u_{1, 0}, \dots, u_{d, 0}), (u_{1, 1},\dots, u_{d, 1}), \dots (u_{1, n}, \dots, u_{d, n})$$
in $\mathbb N^d$ is _r-reversal-bounded_ if for every $1 \le i\le d$ the number of reversal in $(u_{i, 0}, \dots, u_{i, n})$ is bounded by $r$.

We consider counter machines with explicit _nonzero_-tests.

A $d$-counter machine $M = (Q, T, q_0)$ consists of 
- a finite set of states $Q$
- a finite set $T\subseteq Q \times (\mathbb Z^d \cup \{z_1, nz_1, \dots, z_d, nz_d\}) \times Q$ of transitions
- an initial state $q_0\in Q$

A configuration is a pair $(q, \mathbf u) \in Q\times \mathbb N^d$. Consider configurations $(q, \mathbf u), (q', \mathbf u')$ where $\mathbf u = (u_1, \dots, u_d)$ and $\mathbf u' = (u_1', \dots, u'_d)$.
For $\tau\in T$ we define $(q, \mathbf u) \to^\tau (q', \mathbf u')$ if
- $\tau = (q, \mathbf v, q')$ for some $\mathbf v\in\mathbb Z^d$ and $\mathbf u' = \mathbf u + \mathbf v$
- $\tau = (q, z_i, q')$, $u_i = 0$ and $\mathbf u = \mathbf u$
- $\tau = (q, nz_i, q'), u_i \not = 0$ and $\mathbf u = \mathbf u$

> An $r$-reversal-bounded $d$-counter machine or short
> $(d, r)$-RBCM is a $d$-counter machine $M = (Q, T, q_0)$ such that for every run $(q_0, \mathbf 0) \to (q_1, \mathbf u_1) \to \dots \to (q_n, \mathbf u_n)$ the sequence $(\mathbf 0, \mathbf u_1,\dots, \mathbf u_n)$ is $r$-reversal bounded.

> The reachability problem for RBCM is in NP

We make following assumptions:
- The reversal bound of the RBCM is given and unary encoded
- The transitions and target configuration are unary encoded.
- The target configuration is $(q_f, \mathbf 0)$
- All counter updates are elementary (The RBCM is normalized)

> Reachability for nomralized $(d, r)$-RBCM is polynomial-time reducible to reachability for normalized $(d', 1)$-RBCM where $d' = d(r + 1 + \lceil \frac{r+1}{2}\rceil)$.

First, we assume a single counter.

Use $r+1$ many $1$-RB counter $p_1,\dots, p_{r+1}$ to track the phase:
If the counter is in phase $k$ then $p_k = 1$ and $p_j = 0$ for all $j\not=k$.
- Initialize $p_1 = 1$ and $p_i = 0$ for all $i > 1$.
- On every increment or decrement:
	- Guess a number $1 \le k < r+1$ and test $p_k \not = 0$
	- If $k$ is odd and the counter was decremented, or $k$ is even and the counter was incremented, decrement $p_k$ and increment $p_{k+1}$.


From an $r$-RB counter $c$ to $m := \lceil\frac{r+1}{2}\rceil$ many $1$-RB counters $c_1,\dots, c_m$ whose sum is $c$:
Guess the current phase $1\le k\le r+1$ and test $p_k\not = 0$

- Increment $c_{\lceil k/2\rceil}$
- Decrement: guess $1\le i\le m$, check $c_j = 0$ for $j> i$ and decrement $c_i$.
- Zero test: Test all counters $c_1, \dots, c_m$ for zero.
- Nonzero test: Guess $1 \le i\le m$ and test $c_i$ for nonzero

Given a $(1, r)$-RBCM $M = (Q, T, q_0)$ and a target configuration $(q_f, 0)$, we can compute n polynomial time an $(r+1 _ m, 1)$-RBCM $M' = (Q', T', q'_0)$ such that
$$(q_f, 0) \text{ is reachable in } M \iff (q_f, \mathbf 0) \text{ is reachable in } M'$$
For $d > 1$ apply the construction to all counters. This establishes the reduction.

In $(d, 1)$-RBCM, zero test only occur at the start and at the end of a run, with nonzero tests in the middle.

> The reachability problem for normalized $(d, 1)$-RBCM is in NP

Let $M = (Q, T, q_0)$ be a $(d, 1)$-RBCM. We maintain two sets $S$, $E\subseteq \{1, \dots, d\}$:
- $S$ counters which are still zero and will be incremented
- $E$ counters which have reached the final value of zero
The $\mathbb Z$-VASS $V$ simulates $M$ as follows
- If a counter is incremented it is removed from $S$.
- If a counter is decremented it may be added to $E$.
- Counters in $E$ may not be incremented or decremented.

Formally $V$ has states $(q, S, E)\in Q\times 2^{\{1, \dots, d\}}\times 2^{\{1, \dots, d\}}$ and the following transitions
- $(q, S, E) \to^{\mathbf e_i} (q', S\setminus\{i\}, E)$ for all $q \to^{\mathbf e_i} q'$ if $i\not\in E$
- $(q, S, E) \to^{-\mathbf e_i} (q', S, E')$ $(q, S, E)\to^{-\mathbf e_i} (q', S, E \cup \{i\})$ for all $q\to^{-\mathbf e_i} q'$ if $i\not\in E$
- $(q, S, E) \to^{\mathbf 0} (q', S, E)$ for all $q \to^\mathbf 0 q'$
- $(q, S, E) \to^{\mathbf 0} (q', S, E)$ for all $q\to^{z_i} q'$ if $i\in S\cup E$
- $(q, S, E) \to^{\mathbf 0} (q', S, E)$ for all $q\to^{nz_i}q'$ if $i\not\in S\cup E$


We claim that 
$$(q_0, \mathbf 0) \to^*_M (q_f, \mathbf 0) \iff ((q_0, S, E), \mathbf 0) \to^*_v ((q_f, S',\{1, \dots, d\}),\mathbf 0)$$
for some $S, S', E$.

$\implies$: Consider a run $(q_0, \mathbf u_0) \to^{\tau_1}_M \dots \to^{\tau_n}_M (q_n, \mathbf u_n)$ in $M$ with $\mathbf u_0 = \mathbf u_n = \mathbf 0$. Define
- $S_k = \{i | \tau_j \not= \mathbf e_i \text{ for all } j\le k \text{ and } \tau_j = \mathbf e_i \text{ for some } j> k\}$
- $E_k = \{i | t_j \not\in \{-\mathbf e_i, \mathbf e_i\}\text{ for all } j > k\}$
The $((q_0, S_0, E_0), \mathbf u_0) \to_v \dots, \to_v ((q_n, S_n, E_n), \mathbf  u_n)$ is a run.


$\impliedby$
Let $((q_0, S_0, E_0), \mathbf u_0) \to^{\tau_1}_v \dots \to^{\tau_n}_V ((q_n, S_nm E_n), \mathbf u_n)$ be a run with $\mathbf u_0 = \mathbf u_n =\mathbf 0$ and $E_n = \{1, \dots, d\}$.
Then $(q_0, \mathbf u_0) \to_M \dots \to_M (q_n, \mathbf u_n)$
- Increments and decrements can be simulated in $M$
- Suppose that $\tau_k$ is a $\mathbf 0$-transition which originates from a zero-test $(q_{k-1}, z_i, q_k)\in T$. Then $\mathbf u_{k-1} = \mathbf u_k$ and $i\in S_{k-1} \cup E_{k-1}$, at position $k$ counter $i$ was not incremented yet or is not changed again. This implies $\mathbf u_{k-1}(i) = 0$
- Suppose that $\tau_k$ is a $\mathbf 0$-transition which originates from a nonzero-test $(q_{k-1}, nz_i, q_k)\in T$. Then $\mathbf u_{k-1} = \mathbf u_k$ and $i\not\in S_{k-1}\cup E_{k-1}$ at position $k$ counter $i$ was incremented and will be decremented again. This implies $\mathbf u_{k-1}(i) > 0$.


However the $\mathbb Z$-VASS has size $|Q|\cdot 2^{2d}$, but in every run of $V$ the $S$-component is decreasing and the $E$-component is increasing.

- Guess a descending chain $\mathcal S\subseteq 2^{\{1, \dots d\}}$ and an ascending chain $\mathcal E \subseteq 2^{\{1, \dots d\}}\in\mathcal E$ 
- Observe that $|\mathcal S|, |\mathcal E| \le d+1$
- Construct the restriction $V_{\mathcal S, \mathcal E}$ of $V$ to $Q\times \mathcal S\times \mathcal E$ in ptime.
- Guess $S_0, S_f\in\mathcal S$ and $E_0\in\mathcal E$ and test whether 
  $$((q_0, S_0, E_0), \mathbf 0) \to^* ((q_f, S_f, \{1, \dots, d\}), \mathbf 0)$$
  in $V_{\mathcal S, \mathcal E}$.


