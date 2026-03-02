Let $\mathcal A$ be a [Tree Automata](Tree%20Automata.md) $\mathcal A = \{Q, \Sigma, q_0, \Delta, c\}$, the emptiness game $\mathcal G_\mathcal A$ is defined by the [Game](Game.md) between Automata (Player 1) and Pathfinder (Player 1).

- The set of Positions is $Q \cup \Delta$
- Automata controls $Q$, Pathfinder controls $\Delta$
- In a position $q\in Q$ Automata picks a transition $(q, a, l, r)$
- In a position $(q, a, l, r)\in \Delta$ Pathfinder picks $l$ or $r$.
- The winning condition is the parity condition $c$

---

$L(\mathcal A) \not = \emptyset$ iff Automata has a winning strategy on $\mathcal G_\mathcal A$

$\implies$ Assume $L(\mathcal A) \not = \emptyset$, then there is $t\in L(\mathcal A)$ and $\rho$ such that $\mathcal A$ is accepting on $t$. The first $n$ moves of Pathfinder describe a node $u \in\{0, 1\}^n$, a winning strategy for Automata is 
$$\sigma(u) := (\rho(u), t(u), \rho(u0), \rho(u1))$$

Assume Automata has a winning strategy $\sigma$, we construct an accepting run $\rho \in\mathcal T_Q$, the state of node $u\in\{0, 1\}^*$ is defined by the choosing moves of Pathfinder to navigate to node $u$. We claim $\rho$ is accepting, if it were not then $\sigma$ would not be winning for Automata.

By solving $\mathcal G_\mathcal A$ we can test nonemptiness of parity tree automata.

Thus it is decidable if a tree automaton recognizes a nonempty language.

