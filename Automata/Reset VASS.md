A ($d$-dimensional) reset vector addition system with states (reset d-VASS) is a tuple $V = (Q, T, q_0)$, where:
- $Q$ is a finite set of states
- $T \subseteq Q \times (\mathbb Z^d \cup \{r_1, \dots, r_d\}) \times Q$ is a finite set of transitions
- An initial state $q_0 \in Q$.

A configuration is a pair $(q, \mathbf{u}) \in Q \times \mathbb N^d$. Consider $(q, \mathbf{u})$ and
$(q', \mathbf{u}'), \mathbf{u} = (u_1, \dots, u_d)$ and $\mathbf{u}' = (u'_1, \dots, u'_d)$. We write $(q, \mathbf{u}) \to (q', \mathbf{u}')$ if either:
- There is a $(q, \mathbf{v}, q') \in T$ with $\mathbf{v} \in\mathbb Z^d$ and $\mathbf{u}' = \mathbf{u} + \mathbf{v}$ 
- There is a $(q, r_j, q')\in T$ and $$u_i' = \begin{cases} 0 & \text{for } i = j \\ u_i & \text{for } i \not= j\end{cases}$$
