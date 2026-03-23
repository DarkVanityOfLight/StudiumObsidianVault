
For each $m\in\mathbb N$, there is a [VASS](Vector%20Addition%20Systems.md) $\mathcal V = (Q, T, q_0)$ of polynomial size in $m$ such that the [Reachability Set](Reachability%20Set.md) $Reach(\mathcal V)$ is finite, but $|Reach(\mathcal V)| \ge A(m, m)$, where $A$ is the [Ackermann function](Ackermann%20function.md).


Given $m$, we construct a $d$-CASS $\mathcal V_m$ for some $d\in\mathbb N$ of size polynomial in $m$ with distinguished states $q_0$ and $q_1$ such that:
- For any $\mathbf u\in\mathbb N^d$, with $(q_0, \mathbf u)$ as its initial configuration, $\mathcal V_m$ is terminating and
- for every $n\in\mathbb N$, we have $(q_0, (n, \mathbf 0)) \to^* (q_1, (\mathbf 0, A_m (n)))$ 

We construct such a VASS inductively
$\mathcal V_0$:
![](VASS%20have%20large%20reachability%20sets%202026-03-12%2013.27.20.excalidraw)

$\mathcal V_0$ is terminating for every $(q_0, \mathbf u)$ as initial configuration. Also $A_0(n) = n+1$ and 
$$(q_0, (n, 0)) \to^* (q_1, (0, n+1))$$

Suppose we have constructed $\mathcal V_m$, let $\mathcal V_m^{[2, d+1]}$ be $\mathcal V_m$ but using counters $\{2, \dots, d+1\}$ instead of $\{1, \dots, d\}$.

$\mathcal V_{m+1}$
![](VASS%20have%20large%20reachability%20sets%202026-03-12%2013.30.37.excalidraw)

$\mathcal V_{m+1}$ is terminating, every time we take the loop from $q_2$ to $q_2$, the first counter is decremented, but it is never incremented. Thus an infinite run would have to happen insider $\mathcal V_{m}^{[2, d+1]}$, which is impossible by assumption.
Because of $\mathcal V_m$, for $k\ge 0$, we have
$$(q_2, (n, k, \mathbf 0)) \to^* (q_1, (n - 1, \mathbf 0, A_m(k))) \to^* (q_2, (n-1, A_{m}(k), \mathbf 0)).$$
Hence
$$\begin{align}
(q_0, (n, \mathbf 0)) \to^* (q_2, (n+1, 1, \mathbf 0)) \to^* (q_2, (n, A_m(1), \mathbf 0))\\ \to^* (q_2, (1, A_m^n (1), \mathbf 0)) \to^* (q_1, (\mathbf 0, A_m^{n+1}(1))) = (q_1, (\mathbf 0, A_{m+1}(n)))
\end{align}$$


$\mathcal V_m = (Q, T, q_0)$ is an $(m+2)$-VASS with $4m+2$ states and $6m+2$ transitions and $||T|| = 2$. We use this to construct $\overline{\mathcal V}_m$ 
![](VASS%20have%20large%20reachability%20sets%202026-03-12%2013.43.43.excalidraw)
$\overline{\mathcal V}_m = (\overline Q, \overline T, \overline q_0)$ is a $(m+2)$-VASS with $|\overline Q| = 4m+3$ and $|\overline T| = 6m + 3$, and $||\overline T|| \le m+2$. Hence, the size of $\overline{\mathcal V}_m$ is polynomial in $m$. Since $(q_0, \mathbf 0) \to^* (q_1', (\mathbf 0, A_m(m))) = (q_1', (\mathbf 0, A(m, m)))$, we have $|Reach(\overline{\mathcal V}_m)| \ge A(m, m)$. 
$\overline{\mathcal V}_m$ is clearly terminating by construction of $\mathcal V_m$, hence $Reach(\mathcal{\overline V}_m)$ is finite.

