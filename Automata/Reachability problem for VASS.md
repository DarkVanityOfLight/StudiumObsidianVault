> Let $V = (Q, T, q_0)$ be a $d$-[VASS](Vector%20Addition%20Systems.md). A set $I\subseteq Q\times\mathbb N^d$ is an inductive invariant if $\gamma\in I$ implies $post(\gamma) \subseteq I$.

Without proof:
> Let $V = (Q, T, q_0)$ be a $d$-VASS. If $(q, \mathbf u)$ is not reachable then there exists Presburger definable inductive invariant $I\subseteq Q\times \mathbb N^d$ such that $(q_0, \mathbf 0)\in I$ and $(q, \mathbf u)\not\in I$.


> Given a $d$-VASS and Presburger formulas $(\varphi_q(x_1, \dots, x_d))_{q\in Q}$ defining a set $I\subseteq Q\times \mathbb N^d$, one can decide whether $I$ is an inductive invariant.

$$\psi = \forall\mathbf x \bigwedge_{(q, \mathbf v, q') \in T} (\varphi_q(\mathbf x) \land \mathbf x+\mathbf v \ge \mathbf 0 \to\varphi_{q'} (\mathbf x + \mathbf v)$$

Therefore we can enumerate all Presburger definable inductive invariants $I\subseteq Q \times \mathbb N^d$ by enumerating all $|Q|$-tuples of Presburger formulas and testing whether they define an inductive invariant. If we find an inductive invariant $I$ which contains the initial configuration by not the target configuration then we have proved non-reachability.

To (semi) check for reachability, we enumerate all runs.

By combining both semi procedures we can decide reachability in VASS.