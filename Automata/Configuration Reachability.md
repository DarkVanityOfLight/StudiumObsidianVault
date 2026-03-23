
Let $C$ be a class of [Transition Systems](Transition%20System.md). Assume that each transition system in $C$ has a finite description. The _reachability problem_ for $C$, is given the system and two configurations $\gamma_1, \gamma_2 \in \Gamma$ does $\gamma_1 \to^* \gamma_2$.


The configuration reachability problem is undecidable for 4-[Reset VASS](Reset%20VASS.md). We reduce from [2-Counter Automaton](d-Counter%20Automaton.md).
![](20260308_17h04m24s_grim.png)

If the Minsky machine can reach $(q_f, 0,0)$, then the reset VASS can reach $(q_f', 0, 0, 0, 0)$.
We first increment the two new counters to the highest value $M$ used in the run from $(q_0, 0, 0)$ to $(q_f, 0, 0)$, then we always use the corresponding transitions to reach $(q_f, 0, 0, M, M)$, from there we go to $(q_f', 0, 0, M, M)$ and use the loop on $q_f'$ to reach $(q_f', 0, 0, 0, 0)$.

If the reset VASS can reach $(q'_f, 0, 0, 0, 0)$, then the Minsky Machine can reach $(q_f, 0, 0)$:
The run of the reset VASS must visit $(q_f, 0, 0, M, M)$ for some $M\in \mathbb N$, in the run to $(q_f, 0, 0, M, M)$, every transition mimics a corresponding two-counter transition, except possibly the resets.
Suppose a reset is applied to a non-zero counter. Then the sum of the first three counters strictly decreases. However, this sum can never increase, hence it is impossible to reach $(q_f, 0, 0, M, M)$. Therefore, a reset $r_i$ can only happen when the counter $i$ is already zero.
Hence the run of the reset VASS corresponds to a run of the Minsky machine.

