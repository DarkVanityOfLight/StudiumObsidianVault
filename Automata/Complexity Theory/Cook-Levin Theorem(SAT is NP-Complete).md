[SAT](SAT.md) is [NP-Complete](NP-Complete.md) 

---

Clearly $SAT \in NP$ since $\lbrace\langle\varphi, \alpha\rangle | \text{assignment } \alpha \text{ satisfies }\varphi\rbrace \in P$.
Let $L\in NP$ and $M = (Q, \Sigma, \Gamma, \Delta, q_0, F)$ be a 1-tape nondeterministic [TM](Turing%20Machines.md), accepting $L$ in polynomial time $p(n)$.
Then
$$\Delta \subseteq (Q \setminus F) \times \Gamma \times Q\times \Gamma \times \lbrace -1, 0, 1\rbrace$$
Assume $F = \lbrace q_+, q_-\rbrace$ that indicate acceptance/rejection of the TM.

We construct a polynomial time $f$ such that for all inputs $w$:
$$M \text{ accepts } w \iff f(w) \in SAT$$
Let $w = a_1, \dots a_n \in \Sigma^*$ be some input for $M$.
A computation of $M$ on $w$ can be described by a grid on $[-p(n), p(n)] \times [0, p(n)]$
We use variables
- $x_{q, t}$ at time $t$, $M$ is in state $q$
- $y_{a, i, t}$ at time $t$, cell $i$ contains $a$
- $z_{i, t}$ at time $t$ head is at pos $i$

$$\begin{align}
f(w) =& x_{q_0, 0} \land \bigwedge_{i \in (1, n)} y_{a_i, i, 0} \land \bigwedge_{i\not\in[1, n]} y_{\square, i, 0} \land z_{1, 0}\\
&\bigwedge_{t\in[0, p(n) -1], q\in Q\setminus F, a, i} x_{q, t} \land y_{a, i, t} \land z_{i, t} \to \bigvee_{(q, a, q', b, d) \in \Delta} (x_{q', t+1} \land y_{b, i, t+1} \land z_{i+d, t+1})\\
&\land \bigwedge_{t, a, i \not = j} (z_{i, t} \land y_{a, j, t} \to y_{a, j, t+1})\\
&\land \bigvee_t x_{q+it}\\
&\land \varphi_{unique}
\end{align}$$
$f$ is poly-time computable.

