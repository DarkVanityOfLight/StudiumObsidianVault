We say that a game $\mathcal G = \langle A, \text{Win}\rangle$ is regular if $\text{Win}$ is a regular language.
We assume that $\text{Win}$ is given by an [DFA](Deterministische%20endliche%20Automaten.md)/[NFA](Nichtdeterministische%20endliche%20Automaten.md) $\mathcal A_{\text{Win}}$ i.e., $\mathcal G = \langle A, A_{\text{Win}}\rangle$.

This means Player $0$ wins a [play](Play.md) $\pi$ if and only if some non-empty prefix of $\pi$ is accepted by $\mathcal A_{\text{Win}}$


>[!IMPORTANT] Theorem
>Regular games $\mathcal G = \langle A, \text{Win}\rangle$ are determined and can be solved in
> - polynomial time if $\text{Win}$ is given by a DFA
> - exponential time if $\text{Win}$ is given by an NFA

Proof is via reduction to [reachability Games](Reachability%20Game.md), which we already solved.

Given a regular game $\mathcal G = \langle A, \text{Win}\rangle$, where $A = \langle V, E\rangle$ and $\text{Win}$ is given by an NFA/DFA $\mathcal A_{\text{Win}}$, and a vertex $v_0 \in V$.

We first construct a DFA $\mathcal A = \langle Q, \sigma, \delta, q_0, F \rangle$ which accepts all valid plays starting in $v_0$ i.e., following the rules of $A$:

- $Q := V \cup \lbrace q_0\rbrace$ where $q_0 \not \in V$,
- $\Sigma := V$,
- $\delta(q_0, v_0) := v_0$
- for all $(v, v') \in E$ let $\delta(v, v') := v'$
- $F := V$

![|1000](Regular%202024-10-28%2019.31.39.excalidraw)

Let $\mathcal A_{\text{Win}} = \langle Q_{\text{Win}}, V, \delta_{\text{Win}}, q_0^\text{Win}, F_{\text{Win}}\rangle$.
Assume that $\mathcal A_\text{Win}$ is a complete DFA.
We now compute the product automaton
$$\mathcal A_{\times} = \mathcal A \times \mathcal A_{\text{Win}}$$
>[!TIP] Intuition
>$\mathcal A_{\times}$ accepts all valid plays that are contained in $\text{Win}$

We now define the arena $A' = \langle V', E'\rangle$ with
- $V' := Q \times Q_{\text{Win}}$
- $V'_0 := \lbrace (q, q_{\text{Win}}) \in Q \times Q_{\text{Win}} | q \in V_0 \cup \lbrace q_0\rbrace\rbrace$
- $V'_1 := V' \setminus V'_0$
- $E' := \lbrace (x, y) \in V' \times V' | \delta_\times(x, v) = y \text{ for some } v \in V\rbrace$

Player $0$ is winning from $v_0$ in $\mathcal G$ if and only if Player $0$ is winning from $(q_0, q_0^{\text{Win}})$ in the [reachability game](Reachability%20Game.md) $\mathcal G' = \langle A', F \times F_{\text{Win}}\rangle$.

$\implies$
Assume Player $0$ is winning from $v_0$ in $\mathcal G$, i.e. there exists a [winning strategy](Strategy.md#Winning%20Strategy) $\sigma_0: V^* V_0 \to V$ for Player $0$ from $v_0$.
Define the strategy $\sigma_0'$ for Player $0$ from $(q_0, q_0^{\text{Win}})$ in $\mathcal G'$ as follows:

$$\sigma_0'(q_, q_0^{\text{Win}}) := \delta_{\times}((q_0, q_0^{\text{Win}}), v_0)$$

Let $\pi = (q_0, q_0^{\text{Win}})(q_1, q_1^{\text{win}})\dots(q_n, q_n^{\text{Win}})$ with $n\ge 1$, $(q_n, q_n^{\text{Win}}) \in V_0'$, and $\text{suc}(q_n, q_n^{\text{in}}) \not = \emptyset$ be a [play](Play.md) in $\mathcal G'$.

By definition, $q_1\dots q_n$ is a play in $\mathcal G$ with $q_1 = v_0$, $q_n \in V_0$, and $\text{suc}(q_n) \not = \emptyset$. Then
$$\sigma_0'(\pi) := (\delta_0(q_1\dots q_n), q_{\text{Win}})$$
where $q_\text{Win} \in Q_{\text{Win}}$ is the unique state with $((q_n, q_n^{\text{Win}}), (\sigma_0(q_1 \dots q_n), q_\text{Win})) \in E'$. 

We need to show that $\sigma_0'$ is winning for Player $0$ from $(q_0, q_0^{\text{Win}}$:
Let $(q_0, q_0^{\text{Win}})(q_1, q_1^{\text{Win}}) \dots$ be an extended play in $\mathcal G'$ that is conform with $\sigma'_{0}$. By definition, $q_1 \dots$ is an extended play in $\mathcal G$ with $q_1 = v_0$ that is conform with $\sigma_0$.
Thus, since $\sigma_0$ is a winning strategy, there exists a prefix play $q_1 \dots q_n$ with $n \le 1$ such that $q_1 \dots q_n \in \text{Win}$.

Hence, $\mathcal A_\text{Win}$ accepts the word $q_1 \dots q_n$.

Since also $\mathcal A$ accepts $q_1 \dots q_n$, we have that the unique run
$(q_0, q_0^{\text{Win}}),(q_1, q_1^{\text{Win}})\dots,(q_n, q_n^{\text{Win}})$ of $\mathcal A_x$ on $q_1 \dots q_n$ is accepting, i.e.,
$(q_n, q_n^{\text{Win}}) \in F\times F_{\text{Win}}$.
Thus, the play $(q_0, q_0^{\text{Win}})(q_1, q_1^{\text{Win}})\dots(q_n, q_n^{\text{Win}})$ is winning for Player $0$ in $\mathcal G'$, i.e., also the [extended play](Play.md#Extended%20Play) $(q_0, q_0^{\text{Win}})(q_1, q_1^{\text{Win}}) \dots$ is won by Player $0$.

$\impliedby$
Assume Player $0$ is winning from $(q_0, q_0^{\text{Win}})$ in $\mathcal G'$, i.e., there is a [winning strategy](Strategy.md#Winning%20Strategy) $\sigma_0'$ for Player $0$ from $(q_0, q_0^{Win})$.
As already proven, we can assume that the winning strategy is memoryless, i.e., a partial function $\sigma_0' : V_0' \to V'$.
Define the strategy $\sigma_0$ for Player $0$ from $v_0$ in $\mathcal G$ as follows:

Let $\pi = v_0v_1 \dots v_n$ be a play in $\mathcal G$ with $v_n \in V_0$ and $\text{suc}(v_n) \not = \emptyset$.
Since $\mathcal A_\times$ is deterministic, there is a unique play $(q_0, q_0^{\text{Win}})(q_1, q_1^{\text{Win}})\dots(q_{n+1}, q^{\text{Win}}_{n+1}) \not = \emptyset$.
Let $\sigma_0'(q_{n+1}, q_{n+1}^{\text{Win}}) = (q, q_\text{Win})$. Then
$$\sigma_0(\pi) := q$$
We need to show that $\sigma_0$ is winning for Player $0$ from $v_0$:
Let $v_0 \dots$ be an extended play in $\mathcal G$ that is conform with $\sigma_0$.
There exists a unique extended play $(q_0, q_0^{\text{Win}})(q_1, q_1^\text{Win}) \dots$ in $\mathcal G'$ such that $q_{i+1} = v_i$ for all $i \ge 0$.
By definition, this play conform with $\sigma_0'$.
Thus, since $\sigma'_0$ is winning, there exists $n \ge 0$ such that $(q_{n+1}, q_{n+1}^\text{Win}) \in F \times F_\text{Win}$, i.e., Player $0$ wins the reachability game on the prefix play.
Hence, $A_\times$ accepts the word $v_0 \dots v_n$ and, in particular, $v_0 \dots v_n \in \text{Win}$, i.e., the extended play $v_0\dots$ in $\mathcal G$ is won by Player $0$.


## With atomic propositions

A game $\mathcal G = \langle A, \text{Win}\rangle$ with $A = \langle V, E\rangle$ is called regular if there exists a [labeling function](Labeling%20Function.md) $f: V \to \Sigma$ and an automaton $\mathcal A_{\text{Win}}$ over the alphabet $\Sigma$ such that
$$\text{Win} := \lbrace v_0\dots v_n \in V^* | f(v_0\dots v_n) \in \mathcal L(\mathcal A_{\text{Win}})$$
We assume that $\text{Win}$ is given by $\mathcal A_{\text{Win}}$ and $f$, i.e., $\mathcal G = \langle A, \mathcal A_{\text{Win}}, f\rangle$
