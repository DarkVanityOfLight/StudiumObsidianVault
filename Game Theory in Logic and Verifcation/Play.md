A play is a finite non empty sequence $\pi = v_0, v_1v_2 \dots v_n \in V^+$ of vertices such that $v_{i+1} \in \text{suc}(v_i)$ for all $i < n$.

## Extended Play
An extended play is either a play $v_0 \dots v_n$ such that $\text{suc}(v_n) = \emptyset$, i.e., ending in a dead end, or an infinite sequence $v_0 v_1 \dots$ such that $v_0 \dots v_k'$ is a play for all $k \ge 0$.

>[!DEFINITION]
> An extended play is won for Player $0$ if some finite prefix is a winning play for Player $0$. Otherwise, the extended play is won for Player $1$.


