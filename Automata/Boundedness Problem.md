For a vector $\mathbf u \in\mathbb Z^d$ with $\mathbf{u} = (u_1, \dots, u_d)$, let $|| \mathbf u || := |u_1| + \dots + |u_d|$ and $\Sigma \mathbf u = u_1 + \dots + u_d$. By $e_i$, we denote the vector $(0, \dots, 0, 1, 0, \dots, 0)$, where the $1$ is at position $i$.

A [Reset VASS](Reset%20VASS.md) $(Q, T, q_0)$ is bounded if there is a number $k\in\mathbb N$ such that every configuration $(q, \mathbf u)$ with $(q_0, \mathbf 0) \to^* (q, \mathbf, u)$, we have $||u|| \le k$.



The boundedness problem for reset VASS is undecidable.

We construct a 4-[Reset VASS](Reset%20VASS.md) from a s-deterministic accumulating [3-Counter Automaton](d-Counter%20Automaton.md):
![](20260309_11h45m03s_grim.png)
The additional counter is a budget counter.
The new VASS simulates $M$, whenever the counters of $M$ sum to $k$, we can reset the machine and increase the budget counter. 
The budget always decreases by the sum of counter increments, forcing the budget to pay for growth. 

Assume $M$ cannot reach $q_f$, then because $M$ is deterministic, every configuration has a successor and therefore the run is infinite
$$(q_0,u_0) \to (q_1,u_1) \to \cdots$$
Since $M$ is accumulating
$$\|u_0\|,\|u_1\|,\ldots$$
is unbounded.
Thus for any $k$ there exists $i$ such that
$$\|u_i\| \ge k .$$

We construct a run of $V$, by simulating $M$ until $||u|| \ge 1$, there we go to $q^*$, increase the budget and restart. Now simulating until $||u|| \ge 2$ and repeating.

After $k$ phases the budget counter is at least $k$ and therefore $V$ is unbounded.

Conversely assume $V$ is unbounded. Then for every $k$ there exists a run reaching the configuration 
$$(q, u) \text{ with } ||u|| \ge k$$

The only way to increase the number of tokens is via $q^*$, such a run must visit $q^*$ at least $k$ times.

We decompose the run into phases

$$(q_0,v_{1,0}) \to \cdots \to (q^*,v_{1,n_1})$$
$$(q_0,v_{2,0}) \to \cdots \to (q^*,v_{2,n_2})$$

Each phase corresponds to one simulation of $M$.

Resets remove tokens, thus if resets were applied incorrectly, we would lose tokens and could not reach $k$, therefore the phase that increases tokens from $k-1$ to $k$ must correspond to a valid simulation of $M$. Thus in $M$ we reach configuration
$$(q,u) \quad \text{with} \quad \|u\| \ge k .$$
Since this holds for every $k$, $M$ can grow arbitrarily large without reaching $q_f$. Hence $q_f$ is not reachable.


We showed
$$q_f \text{ unreachable in } M \iff V \text{ is unbounded}$$

