

Every Regular Language $L$ has a finite Monoid and an Morphism $\alpha$ such that $M$ [recognizes](Language%20of%20Monoids.md) $L$.

Let $L$ be given as an DFA $A$, every word $w$ induces a state transition in $A$. Take the set of all such state transitions 
$$\tau_w : Q \to Q , \tau_w(q) = \delta(q, w).$$
Notice that there is only finitely many such functions.
Notice that all such $\tau_w$ form a monoid together with composition $$ T(A) := (\{\tau_w | w\in \Sigma^* \}, \circ, id_Q) $$
The function $\alpha: \Sigma^* \to T(A)$ is a morphism since $\tau_{uv} = \tau_u \circ \tau_v$. $\alpha$ recognizes $L$ by
$$L(A) = \{w\in\Sigma^* | \tau_w(q_0) \in F\}$$
and thus
$$L(A) = \alpha^{-1} \text{ where } E := \{\tau \in T(A) | \tau(q_0) \in F\}$$

---

Assume $L$ is recognized by some finite monoid $(M, \cdot, 1_M)$, morphism $\alpha$ and $F$.
Construct the NFA $A$ with state set $M$, transition $\delta(m, a) := m \cdot \alpha(a)$ initial state $1_M$ and final states $F$
