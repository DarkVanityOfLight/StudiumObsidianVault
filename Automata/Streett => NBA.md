
Given a Streett Automaton $\mathcal{A} = (Q, \Sigma, q_0, \delta, \mathcal F)$ with pairs $\mathcal{F} = \{(E_1, F_1), ..., (E_h, F_h)\}$. 
We construct the NBA $\mathcal B$ with states as triples $(q, S_1, S_2)$ 
where $q\in Q$, and each $S_i \subseteq \{1, ..., h\}$ or $S_i = \top$.

The idea is to guess the $F_i$ that will appear infinitely often, and then repeatedly check that all corresponding $E_i$ are reached again and again.

- The state $q$ simulates the behavior of $\mathcal A$
- Initially $S_1 = S_2 = \top$
- At some point non deterministically switch to $S_1 = S_2 = \emptyset$
- If state $q$ is visited, update 
  $$S_1 \leftarrow S_1 \cup \{i | q \in F_i\}, S_2 \leftarrow S_2 \cup \{i | q \in E_i\}$$
- Whenever $S_1 \subseteq S_2$ reset $S_2 = \emptyset$
- $\mathcal B$ accepts if $S_2$ resets infinitely often.


_Claim_ $L(\mathcal A) = L(\mathcal B)$
$L(\mathcal A) \subseteq L(\mathcal B)$. Assume there is a run $\rho$ in $\mathcal A$, let $S$ be the set $F_i$ s that is visited infinitely often, we know that the corresponding $E_i$'s must be visited infinitely often too. After some point only states in $F_i$ are visited. The run in $\mathcal B$ will look like the following, stay in $S_1 = S_2 = \top$ until only $F_i$'s will be visited, after that point we switch $S_1 = S_2 = \emptyset$, because we know that for each $F_i$ the corresponding $E_i$ will be visited at some point repeatedly, we know that eventually $S_1 \subseteq S_2$ infinitely often, and thus we reset $S_2$ infinitely often.

$L(\mathcal A) \supseteq L(\mathcal B)$
Consider a run $\rho'$ in $\mathcal B$, consider the corresponding run $\rho$ in $\mathcal A$, suppose $F_i$ is visited infinitely often then $F_i$ is in $S_1$, since we know $S_2$ is reset infinitely often we know that there is a node in $E_i$ that is visited infinitely often or else $i$ would not be added to $S_2$ and thus not $S_1 \subseteq S_2$, thus $\rho$ is visited infinitely often.

