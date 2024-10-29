
A _strategy_ for Player $i$ is a partial function $\sigma_i : V^* V_i \to V$ that assigns to every prefix $v_0 \dots v_k$ of a play with $v_k \in V_i$ and $\text{suc}(v_k) \not = \emptyset$ a vertex $v\in V$ such that $v \in \text{suc}(v_k)$ and is undefined otherwise.

A [play](Play.md) $v_0 \dots v_n$ is conform with $\sigma_i$ if $v_{k+1} = \sigma(v_0\dots v_k)$ for all $0 \le k < n$ with $v_k \in V_i$.

An [extended Play](Play.md#Extended%20Play) is confirm with $\sigma_i$ if every prefix play is conform with $\sigma_i$ are won for Player $i$.

## Winning Strategy

A strategy $\sigma_i$ for Player $i$ is winning from a vertex $v\in V$ if all extended [plays](Play.md) that start in $v$ and are conform with $\sigma_i$ are won for Player $i$.

## Memoryless Strategy
A strategy $\sigma_i$ for Player $i$ is called memoryless or positional if the value $\sigma_i(v_0 \dots v_k)$ only depends on $v_k$, i.e. the last vertex.

## Finite Memory Strategy
Let $\mathcal G = \langle A, \text{Win}\rangle$ be a game with $A = \langle V, E\rangle$.

A strategy $\sigma_i$ for Player $i$ is finite memory if there exists a complete DFA $\mathcal A_{\sigma_i} = \langle Q, V, \delta, q_0, F\rangle$ and a function $g_{\sigma_i}: V \times Q \to V$ such that if $v_0 \dots v_n$ is a play with $v_n \in V_i$, $\text{suc}(v_n) \not = \emptyset$, and the unique run of $\mathcal A_{\sigma_i}$ on $v_0 \dots v_{n-1}$ reaches the state $q \in Q$, then $\sigma_i(v_0 \dots v_n) = g_{\sigma_i}(v_n, q)$.

> [!IMPORTANT] Theorem
> [Regular Games](Regular%20Games.md) [games](Game.md) $\mathcal G = \langle A, \text{Win}\rangle$ are determined with finite memory winning strategies. Moreover, the winning strategies can be computed in 
> - polynomial time if $\text{Win}$ is given by a DFA
> - exponential time if $\text{Win} is given by an NFA

Let $\text{Win}$ be given by an NFA/DFA $\mathcal A_\text{Win}$ and $v_0 \in V$.
Let $\mathcal G'$ be a reachability game as constructed above from $\mathcal G$ and $v_0$. 
We proved that $\mathcal G$ is determined, i.e., either Player $0$ or Player $1$ is winning from $v_0$.
Assume Player $i$ is winning from $v_0$ and let $\sigma_i'$, be the memoryless winning strategy in $\mathcal G'$ from $(q_0, q_0^{\text{Win}})$, which by the above proposition exists.
We define the finite memory strategy $\sigma_i$ using $\mathcal A_{\text{Win}}$ as $\mathcal A_{\sigma_i}$ and
$$g_{\sigma_i}(v, q_\text{Win}) := \begin{cases}
v', &\text{if } \sigma'_i(v, q_{\text{Win}}) = (v', q'_\text{Win}) \text{ is defined}\\
\text{any } v' \in V,&\text{otherwise}
\end{cases}$$
for all $v\in V$ and $q_\text{Win} \in Q_\text{Win}$

We need to show that $\sigma_i$ is winning for Player $i$ from $v_0$.
Let $v_0\dots$ be an extended play in $\mathcal G$ that is conform with $\sigma_i$.
By definition, there is an [extended play](Play.md#Extended%20Play) in $\mathcal G'$ is won by Player $i$. Hence, the extended play $v_0\dots$ in $\mathcal G$ is won by Player $i$, using the same reasoning as in the propositions.

