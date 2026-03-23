---
aliases:
  - VASS
---

A ($d$-dimensional) vector addition system with states ($d$-VASS) is a [tuple](Tuple.md) $V = (Q, T, q_0)$, where
- $Q$ is a finite [set](Mengen.md) of states
- $T \subseteq Q \times \mathbb Z^d \times Q$ is a finite set of transitions
- an initial state $q_0 \in Q$

A _configuration_ is a pair $(q, \textbf{u}) \in Q\times \mathbb N^d$. 
We write $(q, \textbf{u}) \to (q', \textbf{u}')$ if there is a $(q, \textbf{v}, q') \in T$ with $\textbf{u}' = \textbf{u} + \textbf{v}$.
We write $(q, \textbf{u}) \to^* (q', \textbf{u}')$ if there is a sequence
$$(q_0, \textbf{u}_0) \to (q_1, \textbf{u}_1) \to \dots \to (q_n, \textbf{u}_n)$$
