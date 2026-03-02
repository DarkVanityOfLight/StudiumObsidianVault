
If $g$ is [space constructible](Space%20Constructible%20Functions.md) and $f\in o(g)$, that is $\forall c > 0 \exists n_0 \forall n \ge n_0 c \cdot f(n) \le g(n)$ then $DSPACE(f) \subset DSPACE(g)$
(see [DSPACE(f)](DSPACE(f).md))


Let $D$ be a TM with the following behavior on input $x$:
- Compute $1^{g(n)}$, and mark the work tape of $g(n)$ cells on all tapes
- Run the universal TM $U$ on $\langle M_x, x\rangle$ 
- If the simulation of $U$ leaves the marked work space, $D$ halts and outputs anything.
- If an output $b\in\lbrace 0, 1\rbrace$ return $1-b$

Then $L(D) \in DSPACE(g) \setminus DSPACE(f)$
$D$ clearly uses $O(g)$ space.
Towards a contradiction we assume there exists a $f$ space bounded TM $M$ with $L(M) = L(D)$. Let $x$ be an encoding of $M$. Then:
$$D(x) = 1-M_x(x) =  1 - M_x = 1-D(x)$$

assuming that the simulation of $U$ on $\langle M_x, x\rangle$ uses at most $g(|x|)$ space. This would be a contradiction

The space to simulate $M$ by $U$ on any input $y$ is bounded by $c\cdot f(|y|)$ where $c$ only depends on $M$.
Let $n_0$ be such that $c \cdot f(n) \le g(n)$ for all $n\ge n_0$. Pick an encoding $x$ of $M$ with $|x| \ge n_0$

Hence
$$L = DSPACE(\log n) \subset DPSACE(\log n^2) \subset DSPACE(n) \subset DSPACE(n^2) \subset PSPACE$$
