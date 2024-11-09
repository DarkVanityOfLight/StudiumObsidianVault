
Given an Arena $A = \langle V, E\rangle$ with $V = V_0 \cup V_1$, we denote the swap of player states by $\overline V$, that is
$\overline V = V_0' \cup V_1'$ with $V_0' = V_1$ and $V_1' = V_0$


 Given two arenas $A_1 = \langle V^1, E_1 \rangle$ and $A_2 = \langle V^2, E_2\rangle$, the union $A' = A_1 \cup A_2$ is defined as $A' := \langle V^1 \cup V^2, E_1 \cup E_2 \rangle$
 
 Given a valuation $F$ and a circuit $C$, write $F[C]$ for evaluation of circuit $C$ under $F$

To reduce BCE to a reachability game $G = \langle A, T \rangle$, we construct following arena for a given circuit $C$ and assignemnt $F$ via induction over the circuit. Assume the circuit has no constants, these can easily replaced by variables and their corresponding assignment, also assume no variable is used twice, this can be done by introducing new variables with the same assignment, for ease of notation we overload the denotions for (sub)circuits and vertices:


We construct a game $G = \langle A, T\rangle$ with arena
$A = \langle V, E \rangle$, where $V = V_0 \cup V_1$ as follows.

__Base Case__
- Atom $x_i$, create vertex $x_i \in V_0 \iff F[x_i] = \top$ or $x_i\in V_1 \iff F[x_i] = \bot$. If $F[x_i] = \top$ add it to the target set $T$.

Let $s$ be the set of atoms in a subcircuit.
Define $\overline{T} := \lbrace s \setminus T\rbrace$

__Inductive step__
Let $G_1 = \langle A_1, T_1 \rangle$ and $G_2 = \langle A_2, T_2 \rangle$
Let $A_1 = \langle V^1, E_1\rangle$ and $A_2 = \langle V^2, E_2\rangle$ be the Arena of the already reduced subcircuits,
let $c_1$ and $c_2$ be the vertex of the 'topmost' gate of each reduced circuits.

Denote the resulting Arena by $A' = \langle V', E'\rangle$, and the game by $G' = \langle A', T'\rangle$

- $\neg c_1$: $G' = \langle A_1, \overline T_1\rangle$ $A' = \langle \overline{V^1}, E_1 \rangle$
- $c_1 \land c_2$: $G' = \langle A_1 \cup A_2, T_1 \cup T_2 \rangle$, create a vertex $c_i \in V_1'$, add edges $(c_i, c_1)$ and $(c_i, c_2)$ to $E'$
- $c_1 \lor c_2$: $G' = \langle A_1 \cup A_2, T_1 \cup T_2 \rangle$, create a vertex $c_i \in V_1'$, add edges $(c_i, c_1)$ and $(c_i, c_2)$ to $E'$
