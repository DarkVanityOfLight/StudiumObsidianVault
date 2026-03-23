---
aliases:
  - 2-PDA
  - PDA
---

A $d$-pushdown Automaton is a tuple $(Q, \Gamma, T, q_0)$, where
- $Q$ is a finite set of states
- $\Gamma$ is a stack alphabet
- $T\subseteq Q\times \{\gamma_i, \overline\gamma_i, \epsilon | i\in \{1, ..., d\}\} \times Q$ 
- $q_0 \in Q$ is its initial state

We will continue defining 2-pushdown automata(2-PDA), $d$ is analog
A configuration is a $d$-tuple $(q, u, v) \in Q \times \Gamma^{*} \times \Gamma^*$ 
We write $(q, u_1, u_2) \to (q', u'_1, u'_2)$ if there is a $(q, w, q') \in T$ with:
- If $w = \gamma_i$, then append $\gamma$ to $u_i: u_i' = u_i\gamma$
- If $w = \overline\gamma_i$, then remove $\gamma$ from $u_i: u_i = u_i'\gamma$

We write $(q, u_1, u_2) \to^* (q', u_1', u_2')$ if there is a sequence
$$(q_0, u_1^{(0)}, u_2^{(0)} \to q_1, u_1^{(1)}, u_2^{(1)} \to \dots \to q_n, u_1^{(n)}, u_2^{(n)}$$



_State reachability for 2-PDA is undecidable_
We reduce to the halting problem of [TM](Turing%20Machines.md)'s, we use a variation where a configuration has the form
$$uqv$$
with
- $u, v \in \Gamma^*$ 
- $q\in Q$
where the head reads the last symbol of $u$.

This configuration can be represented by a 2-PDA configuration
$$(q, u, v^{rev})$$
Such that Stack 1 stores $u$, Stack 2 stores the reverse of $v$.

To simulate a transition in the TM we distinguish the following cases:
- _Move Left:_ Pop Symbol $x$ from Stack 1 and push $x$ to Stack 2
- _Move Right:_ Pop and Push $x$ from Stack 1, to ensure we are reading the correct symbol, then pop any symbol $\overline\gamma$ from stack 2 and push $\gamma$ to stack 1
- _Replacing a Symbol:_ Pop $\overline x$ from Stack 1 and push $y$ to stack 2
- _Inserting a new Symbol:_ Pop and Push $x$ from/to Stack 1 to verify that we read the correct symbol, then push $y$ to the first stack.

