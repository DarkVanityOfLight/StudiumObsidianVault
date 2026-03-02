A parity tree automaton $\mathcal A = (Q, \Sigma, q_0, \Delta, c)$ is
- A finite state set $Q$
- A finite alphabet $\Sigma$
- An initial state $q_0$
- A transition relation $\Delta \subseteq Q \times \Sigma \times Q \times Q$
- A color function $c: Q \to \{1,..., k\}$


A run of $\mathcal A$ on a tree $t \in \mathcal T_\Sigma$ is a tree $\rho \in \mathcal T_Q$ with $\rho(\varepsilon) = q_0$ and
$$(\rho(u), t(u), \rho(u0), \rho(u1)) \in \Delta \quad \forall u\in\{0,1\}^*$$

$\rho$ is accepting if the parity condition holds on all paths $\pi$.
A tree $t\in \mathcal T_\Sigma$ is accepted by $\mathcal A$ if there is an accepting run of $\mathcal A$ on $t$.

---

Let $\Sigma$ be a finite alphabet, an infinite (binary) tree is a mapping

$$t: \{0, 1\}^* \to \Sigma$$

The set of all infinite trees over $\Sigma$ is denoted $\mathcal{T}_\Sigma$. 

A path is an infinite word $\pi \in\{0, 1\}^\omega$. Given a tree $t\in \mathcal{T}_\Sigma$ and a path $\pi$ define:
$$t|_\pi := t(\varepsilon)t(\pi(0))t(\pi(0)\pi(1))t(\pi(0)\pi(1)\pi(2))$$
