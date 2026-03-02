A **reachability game** is a game $\mathcal{G} = \langle A, \text{Win} \rangle$ where there exists the[Arena](Arena.md) $A$, a target set $T\subseteq V$, and a positive integer $n$, such that the winning condition for **Player 0** is to reach a vertex in $T$ within at most $n$ steps, while **Player 1** tries to prevent this.

 __Player 0__ [wins](Game.md#Winning) with:
$$\text{Win} = \lbrace v_0v_1 \dots v_i \in V^+\rbrace | v_i \in T \text{ for some } 0 \le i \le n\rbrace$$
that is to reach a vertex in $T$ in smaller then $n$ steps.


---

> [!IMPORTANT] Proposition
> For a reachability game $\mathcal G = \langle A, T\rangle$, we have $W_0 = Attr_0(T)$ and $W_1 = V\setminus Attr_0(T)$.

__Proof:__
We define a distance function on every $v\in V$ as 
$$\text{dist(v)} := \begin{cases}
\min\lbrace j\in \lbrace 0, \dots, |V| \rbrace | v \in Attr^j_0(T)\rbrace, &\text{if $v\in Attr_0(T)$}\\
\infty &\text{otherwise}
\end{cases}$$
that is the smallest number of steps to force a visit of a vertex in $T$ from $v$, if possible, otherwise $\infty$.

- From a vertex $v\in Attr_0(T)\setminus T$:
	- if $v \in V_0$, then there is $v' \in \text{suc}(v)$ such that $\text{dist}(v') < \text{dist}(v)$
	- if $v\in V_1$, then for all $v' \in \text{suc}(v)$ we have $\text{dist}(v') < \text{dist}(v)$ 
- From a vertex in $v\in V\setminus Attr_0(T)$ with $suc(v) \not = \emptyset$
	- if $v\in V_0$, then for all $v' \in \text{suc}(v)$ we have $v' \not \in Attr_0(T)$ 
	- if $v\in V_1$, then there is $v'\in suc(v)$ such that $v' \in Attr_0(T)$

---

>[!IMPORTANT] Theorem
>Reachability games are determined with memoryless winning strategies and can be solved in polynomial time.

__Proof:__
A [Memoryless Strategy](Strategy.md#Memoryless%20Strategy) $\sigma_0$ for Player $0$ can be defined for all $v\in V_0$ with $\text{suc}(v) \not = \emptyset$ as:
$$\sigma_0(v) := \begin{cases}
\text{any } v' \in \text{suc}(v) \text{ s.t. } \text{dist}(v') < \text{dist}(v), & \text{if } v \in Attr_0(T)\setminus T\\
\text{any } v' \in suc(v), &\text{otherwise}
\end{cases}$$
A [Memoryless Strategy](Strategy.md#Memoryless%20Strategy) $\sigma_1$ can be similarly defined for Player $1$ can be defined for all $v\in V_1$ with $\text{suc}(v) \not = \emptyset$

$$\sigma_1(v) := \begin{cases}
\text{any } v' \in \text{suc}(v) \text{ s.t. } v' \not \in Attr_0(T), & \text{if } v \in Attr_0(T)\\
\text{any } v' \in suc(v), &\text{otherwise}
\end{cases}$$

