
The syntactic monoid $M$ is the unique(up to isomorphism) smallest monoid of some regular language $L$, that recognizes $L$.
It is isomorphic to the Transition monoid of the minimized DFA.

It is defined by 
$$ \text{Syn}(L) := \Sigma^* / \sim_L $$
Membership in $L$ is determined by the class of $[w]_{\sim_L}$ 

## Syntactic Congruence
Let $L$ be a language, the syntactic congruence of $L$ is the equivalence relation $\sim_L$ defined by
$$ u \sim_L v \iff \forall s, t\in \Sigma^* (sut \in L \iff svt \in L) $$

## Computing the Syntactic Monoid

If $A$ is the minimal DFA of a regular language then $T(A)$ is isomorphic to $\text{Syn(L)}$.

$$\alpha: \Sigma^*/\sim_L \to T(A), [w]_{\sim_L} \mapsto \tau_w$$

To verify well-definedness and injectivity, we show
$$v_1 \sim_L v_2 \iff \tau_{v_1} = \tau_{v_2}.$$
First, assume $\tau_{v_1} = \tau_{v_2}$. Then for all $u,w \in \Sigma^*$,
$$\tau_{u v_1 w} = \tau_{u v_2 w},$$
hence
$$\delta(q_0, u v_1 w) = \delta(q_0, u v_2 w).$$
Therefore
$$u v_1 w \in L \iff u v_2 w \in L,$$
so $v_1 \sim_L v_2$.
Conversely, assume $v_1 \sim_L v_2$ but $\tau_{v_1} \neq \tau_{v_2}$. Then there exists $q \in Q$ such that
$$\delta(q, v_1) \neq \delta(q, v_2).$$
Choose $u$ with $\delta(q_0, u) = q$. Since $A$ is minimal, the states $\delta(q, v_1)$ and $\delta(q, v_2)$ are distinguishable by some word $w$. Hence
$$\delta(q_0, u v_1 w) \in F \iff \delta(q_0, u v_2 w) \notin F,$$
which contradicts $v_1 \sim_L v_2$.