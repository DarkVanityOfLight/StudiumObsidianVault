

There are functions $f$ so that $DTIME(f) =  DTIME(2^f)$


Let $r(n) \ge n$ be a computable monotonic function.
There exists a computable increasing function $s$ such that 
$$DTIME(s) = DTIME(r \cdot s)$$

>[!OBSERVATION]
> $DTIME(s) \subseteq DTIME(r\cdot s)$ because $r(n) \ge n$ and $s(n) \le r(s(n))$

We show $\supseteq$: In the following let $(M_k)_{k\in\mathbb N}$ be an effective enumeration of all deterministic [TMs](Turing%20Machines.md) (view the binary encoding aof a TM as a number). Define $t_k(n) \in\mathbb N \cup \lbrace \infty\rbrace$ be the maximal running time of $M_k$ on all inputs of length $\le n$.

Define
$$T_n = \lbrace t_k(n) | k\in [1, n]\rbrace$$

Later we choose $s(n)$ such that 
$$T_n \cap [s(n), r(s(n))] = \emptyset$$ for all $n$.


Let $L \in DTIME(r \cdot s)$ be accepted by a $(r\cdot s)$-time bounded TM $M_k$. Then
$$t_k(n) \le r(s(n)) \qquad \forall n\in\mathbb N$$
by definition of being $(r\cdot s)$-time bounded.

For $n\le k$, implies $t_k(n) < s(n)$, since otherwise $t_k(n) \in T_n \cap [s(n), r(s(n))]$.

Therefore $M_k$ in fact halts after $\le s(n)$ steps if $n\ge k$. For shorter inputs $n < k$, a TM can test whether $n < k$ and test membership to $L$ in $n = O(1)$ steps => $L\in DTIME(s)$

Weh use the following algorithm for $s(n)$:

1. If $n=1$ return $1$
2. Set $s = s(n-1) + 1$
3. Increment $s$ until $\forall k\in [1, n) \cdot t_k(n) \not\in [s, r(s)]$

Step 3 can be verified by simulating $M_k$ on all inputs of length $\le n$ for at most $r(s(n)) + 1$ steps, and checking whether it has a maximal running time in $[s, r(s)]$.


