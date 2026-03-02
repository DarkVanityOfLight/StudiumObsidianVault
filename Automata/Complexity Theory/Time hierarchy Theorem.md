
If $g$ is [time constructible](Time%20constructible.md) and $f$ satisfies $f(n) \cdot \log f(n) \in o(g)$ then $DTIME(f) \subset DTIME(g)$.


Let $D$ be a [TM](Turing%20Machines.md) which on input $x$ does the following:
- Compute $1^{g(n)}$ where $n = |x|$ on a special "counter" tape.
- Simulate the unviersal TM $U$ on $\langle M_x, x\rangle$ for $g(n)$ steps.
- If an output $b\in\lbrace 0, 1\rbrace$ is produced return $1-b$, and otherwise return anything.

>[!OBSERVATION]
> $D$ always halst in $O(g(n))$ time since $g$ is time constructible.


$L(D) \not \in DTIME(f)$
Suppose $M = M_x$ is $f$ time bounded and $L(D) = L(M)$.
$$D(x) = 1 - M_x(x) = 1 - M(x) = 1 - D(x)$$
assuming that the simulation of $U$ on $\langle M_x, x\rangle$ halts in $g(|x|)$ steps. The time to simulate $M$ by $U$ on any input $y$ is:
$$\le c \cdot f(|y|) \cdot \log f(|y|)$$
where $c$ does not depend on $y$.

Pick an encoding $x$ on $M$ with $|x| \ge n_0$.
Then the simulation of $M$ on $x$ takes time $\le g(|x|)$.

$$DTIME(n) \subset DTIME(n - \log n) \subset DTIME(n^2) \subset \dots \subset P$$

