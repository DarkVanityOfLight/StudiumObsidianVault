
We consider [VASS](Vector%20Addition%20Systems.md) where the counters range over $\mathbb Z$ instead of $\mathbb N$.

A $d$-dimensional integer VASS $V = (Q, T, q_0)$ is syntactically the same as a $d$-dimensional VASS. Configurations in $V$ are pairs $(q, \mathbf u) \in Q \times \mathbb Z^d$, and we define $(q,\mathbf u) \to (q', u')$ if there exists $(q, \mathbf v, q')\in T$ such that $\mathbf u' = \mathbf u + \mathbf v$.

$\mathbb Z$ VASS are an overapproximation of VASS, the [Reachability Set](Reachability%20Set.md) of a $\mathbb Z$ VASS $V$ contains the reachability set of $V$ viewed as a VASS.

[Presburger Arithmetic is decidable](Presburger%20Arithmetic%20is%20decidable.md).

Given a $d$-dimensional $\mathbb Z$-VASS and a state $q_f\in Q$, one can compute in linear time an existential Presburger formula defining $\{\mathbf u\in\mathbb Z^d | (q_0,\mathbf 0) \to^* (q_f, \mathbf u)\}$.

Let $T = \{\tau_1, \dots, \tau_k\}$ be the set of transitions where $\tau_i$ has effect $\mathbf v_i\in\mathbb Z^d$. We view $V$ as an [NFA](Nichtdeterministische%20endliche%20Automaten.md) $\mathcal A = (Q, \{\mathbf v_1, \dots, \mathbf v_k\}, T, q_0, \{q_f\})$. In linear time we construct an existential Presburger formula $\varphi_\mathcal A (x_1, \dots, x_k)$ defining the Parikh image of $L(\mathcal A)$. Then
$$\varphi(\mathbf y) = \exists \mathbf x(\varphi_\mathcal A(\mathbf x) \land \mathbf y = \sum^k_{i=1} x_i\mathbf v_i$$
defines the set of reachable configurations $(q_f, \mathbf u)$.

Since PA is in NP, we obtain
> The reachability problem for $\mathbb Z$-VASS is in NP

