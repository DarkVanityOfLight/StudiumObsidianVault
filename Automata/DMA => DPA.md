
Given the DMA $\mathcal{A} = (Q, \Sigma, q_0, \delta, \mathcal F)$ where we construct a DPA using a Least appearance record.

Each state is a Least Appearance Record, which is a permutation
$(i_1, ..., i_n)$ of $\{1, ..., n\}$ together with an index $h \in \{1, ..., n\}$ called the hit position.

The initial LAR is $(\underline 1, ..., n)$. We shift the new state $q$ to the left and set the hit to the position of $q$ in the previous permutation.




Let $\rho$ be the run in $\mathcal A$ and $\rho'$ be the run in $\mathcal B$. Let $F \subseteq Q$ be a subset, and $|F| = m$. Then $inf(\rho) = F$ iff
1. The hit position is only finitely many times larger then $|m|$
2. Infinitely often the hit position is $= m$ and the first $m$ states in the permutation for the set $F$


Assume $inf(\rho) = F$, then after some finite prefix only states $q\in F$ appear, thus the first $1...m$ states of the permutation eventually will only be from $F$. Thus the hit eventually stays $\le m$. 
For condition 2. assume the hit eventually stays $< m$, then $i_m \in F$ is visited only finitely many often, this is a contradiction.

Assume condition 1. and 2. hold, then $inf(\rho) = F$.
By condition 1. states $i_{m+1}... i_{n}$ are visited only finitely many times. We still have to show that $\{i_1, ..., i_m\}$ is visited infinitely many times. Towards a contradiction we assume there is a $q$ that is only visited finitely many times, then eventually $q$ will be at position $m$ because of condition 2., which in turn means it is visited infinitely often, since infinitely often the hit is at position $m$.



From this we can construct the following parity condition

$$c(i_1, ... i_h .... i_n) = \begin{cases}
2h & \text{if } \{i_1, ..., i_h\}\in \mathcal F\\
2h - 1 &\text{if } \{i_1, ..., i_h\}\not\in \mathcal F
\end{cases}$$





