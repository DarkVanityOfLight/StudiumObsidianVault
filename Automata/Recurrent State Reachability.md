Suppose we have a class $C$ of systems, such that all configurations have a finite-state component. The _recurrnt state reachability_ problem is asking given a system $S$ from the class $C$ and a state $q$ of $S$, is there an infinite run that visits $q$ infinitely often.


Recurrent Reachability problem is undecidable for the class of [Reset VASS](Reset%20VASS.md)

![](20260308_17h15m09s_grim.png)

We show two directions:

If the Minsky Machine can reach $(q_f, 0, 0)$, then the reset VASS can reach $q_f'$ recurrently:
We first increment the new counter to the highest value $M$ used in the run from $(q_0, 0, 0)$ to $(q_f, 0,0)$, then we always use the new corresponding transitions to reach $(q_f, 0, 0, M)$. From there go to $(q_0, 0,0)$ and perform the same run again.

If the reset VASS can reach $q'_f$ recurrently, then the Minsky Machine can reach $(q_f, 0, 0)$:

The run of the reset VASS must visit $q'_f$ infinitely often. Right afterwards, it enters the configuration $(q_0, 0, 0, n), n\in\mathbb N$. Suppose a reset is applied to a non-zero counter. Then the sum of the counters strictly decreases. However, this sum can never increase, such a mistake can occur only finitely many times during the run. After this, all resets must be performed on zero. Thus eventually, every visit of $q'_f$ follows a visit of $(q_f, 0, 0, n)$. Moreover, all but finitely many of those phases are from $(q_0, 0, 0, n)$ to $(q_f, 0, 0, n)$ and must be runs of the Minsky machine from $(q_0, 0, 0)$ to $(q_f, 0, 0)$.

