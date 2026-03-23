The [Parikh image](Parikh%20image.md) of a context-free language is effectively [semilinear](Semilinear%20sets.md).


We will show that the Parikh image of a context-free language is definable by an existential Presburger formula whose length is linear in the grammar size.

---

We will start with something simpler:
> Given an [NFA](Nichtdeterministische%20endliche%20Automaten.md) $\mathcal A$ one can compute in linear time an existential Presburger formula defining the Parikh image of $L(\mathcal A)$.

Let $\mathcal A = (Q, \Sigma, E, q_{in}, F)$ be an NFA where $E\subseteq Q \times \Sigma \times Q$. For simplicity we assume that $F$ contains a single final state $q_f$.
- We write $q \to^\tau q'$ if $\tau = (q, a', q')$ for some $a\in\Sigma$
- A run $\pi$ is a sequence $q_0 \to^{\tau_1} q_1 \to^{\tau_2} \dots\to^{\tau_n} q_n$
- $\pi$ is accepting if $q_0 = q_in$ and $q_n = q_f$.

Instead of letters we count transitions.

> The Parikh image of a run $\pi$ is the vector $\mathbf x = (x_\tau)_{\tau\in E} \in \mathbb N^E$ where $x_\tau$ is the number of occurrences of $\tau$ in $\pi$.

The Parikh vector $\mathbf x$ satisfies a "flow condition". In every state the number of times an incoming transition is used is equal to the number of times an outgoing transition is used(except for the initial and the final state)

$out(q) := \{\tau \in E | \tau \text{ starts in } q\}$
$in(q) := \{\tau \in E | \tau \text{ ends in } q\}$

Given a Parikh vector $\mathbf x\in\mathbb N^E$ we obtain an automaton/graph by removing from $\mathcal A$ all transitions and states which are not used in $\mathbf x$. Formally, we define the _graph_ $N[\mathbf x] = (Q[\mathbf x], E[\mathbf x])$ where
- $E[\mathbf x] := \{\tau\in E | x_\tau > 0\}$
- $Q[\mathbf x] = \{q\in Q | q\text{ occurs in some } \tau\in E[\mathbf x]\}$


Define $\delta_{a, b} =  1$ if $a = b$ and $\delta_{a, b} = 0$ otherwise.

> There exists an accepting run with Parikh image $\mathbf x\in\mathbb N^E$ in $\mathcal A$ iff for all $q\in Q$ we have
> $$\sum_{\tau \in out(q)} x_\tau - \sum_{\tau\in in(q) x_\tau = \delta_{q, q_in} - \delta_{q, q_f}}$$
> and all states in $N[\mathbf x]$ are reachable from $q_in$.

($\implies$)
Consider an accepting run $q_0 \to q_1 \to \dots \to q_n$. If $q$ occurs $k$ times amongst $q_1, \dots, q_{n-1}$ then
- $q$ occurs $k$ times as a source state of a transition plus another occurrence if $q = q_{in}$
- $q$ occurs $k$ times as a target state of a transition plus another occurrence if $q = q_f$
Clearly, all states in $N[\mathbf x]$ are reachable from $q_{in}$ via the run

($\impliedby$): By induction on $\sum_{\tau\in E} x_\tau$. If $\mathbf x =\mathbf 0$ then $q_{in} = q_f$. The empty run is accepting and has Parikh image $\mathbf 0$. Now assume $\mathbf x \not = \mathbf 0$. We distinguish two cases:
- Assume that $q_{in}$ is contained in a cycle $C$ of $N[\mathbf x]$. If $\tau = (q_{in}, a, p)$ lies on $C$ then all states in $N[\mathbf x - \mathbf e_\tau]$ are reachable from $p$.
- Otherwise $q_{in}$ has no incoming transition in $N[\mathbf x]$ and exactly one outgoing transition $\tau = (q_{in}, q, p)$ in $N[\mathbf x]$. Again, all states in $N[\mathbf x - \mathbf e_\tau]$ are reachable from $p$.

In any case we find a transition $\tau = (q_{in}, a, p)$ such that all states in $N[\mathbf x - \mathbf e_\tau']$ are reachable from $p$. Setting $\mathbf x' = \mathbf x - \mathbf e_\tau$ we obtain:
$$\begin{align}
\sum_{\tau\in out(q)} x_\tau' - \sum_{\tau\in in(q)} x'_\tau &= \sum_{\tau\in out(q)} x_\tau - \sum_{\tau\in in(q)} x_\tau - \delta_{q, q_{in}} + \delta_{q, p} \\
& = \delta_{q, q_{in}} - \delta(q, q_{in}) + \delta_{q, p}\\
&= \delta_{q, p} - \delta_{q, q_f}
\end{align}$$
Therefore, by induction there is a run from $p$ to $q_f$ with Parikh image $\mathbf x'$. Adding the transition $\tau$ we obtain the desired run from $q_{in}$ to $q_f$.

We are now ready to proof the main theorem. To express the reachability condition, we describe the existence of a spanning tree of $N[\mathbf x]$ rooted in $q_{in}$. To every state $q\in Q$ we assign a distance $y_q \in\mathbb N$ to $q_{in}$.

We use variables $\mathbf x = (x_\tau)_{\tau\in E}$, and $\mathbf y = (y_q)_{q\in Q}$, $\mathbf z = (z_a)_{a\in\Sigma}$, then
$$\varphi(\mathbf z) := \exists \mathbf x\mathbf y. \bigwedge_{q\in Q} (\alpha_q \land \beta_q) \land \bigwedge_{a\in\Sigma} \gamma_a$$
defines the Parikh image of $L(\mathcal A)$ where the subformulas are
$$\alpha_q := \sum_{\tau\in out(q)} x_\tau - \sum_{\tau\in in(q)} x_\tau = \delta_{q, q_{in}} - \delta_{q, q_f}$$
$$\beta_{q_{in}} := y_{q_{in}} = 1$$
$$\beta_q := \bigvee_{p, a, q\in(q)} (x_{p, a, q} > 0 \land y_p > 0 \land y_q = y_p + 1) \lor \sum_{\tau\in in(q)} x_\tau = 0 \to y_q = 0$$
$$\gamma_a := z_a = \sum_{\tau\in E\text{ reads } a} x_\tau$$

---

> Given a [Context free grammar](Context%20free%20grammar.md) $G$ one can compute in linear time an existential Presburger formula defining the Parikh image of $L(G)$.

The formula for $\psi(L(G))$ will use the following variables:
- $x_p$ for each $p\in P$
- $y_X$ for each $X\in V$
- $z_a$ for each $a\in\Sigma$


For $X\in V$ and $p = (Y\to u)\in P$ we set $X(p) = 1$ if $X = Y$ and $X(p) = 0$, otherwise. Furthermore, we write $|p|_X = |u|_X$.

For each $X\in V \setminus \{ S \}$ we define 
$$\alpha_X := \sum_{p\in P} X(p) \cdot x_p = \sum_{p\in P} |p|_X \cdot x_p$$
and
$$\alpha_S := \sum_{p\in P} S(p) \cdot x_p = 1+ \sum_{p\in P} |p|_s \cdot x_p$$
The formula says that a variable $X$ is produced as often as it is consumed (exception: $S$).

We define 
$$\beta_S := y_s = 1$$
and for each $X \in V \setminus \{S\}$ we define
$$\beta_X := \left( y_X =0 \land \sum_{p\in P} |p|_X \cdot x_p = 0  \right) \lor \bigvee_{(Y\to u)\in P; |u|_X > 0} (x_{Y\to u} > 0 \land y_Y > 0 \land y_X = y_Y + 1).$$
We number the non terminals $X$ occurring in the derivation tree by an index $y_X$. If $X$ does not occur then $y_X = 0$.

For each $a\in \Sigma$ we define
$$\gamma_a := \left( z_a = \sum_{p\in P} |p|_a \cdot x_p \right)$$
The formula $\gamma_s$ counts how often the letter $a$ is produced in productions.

The final formula for the Parikh image is:
$$\varphi(\mathbf z) := \exists \mathbf x\exists \mathbf y. \bigwedge_{X\in V} (\alpha_X \land \beta_X) \land \bigwedge_{a\in\Sigma} \gamma_a.$$

We claim that $\varphi$ defines $\psi(L(G))$. Suppose that $w\in L(G)$, that is there exists a derivation tree $T$ for $w$. Define $x_p$ the number of times production $p$ is applied in $T$ and define $z_a = |w|_a$. Clearly, $(\mathbf x, \mathbf z)$ satisfies $\bigwedge_{X\in V} \alpha_X \land \bigwedge_{a\in\Sigma} \gamma_a$.
The indices $y_X$ are defined inductively.
- Set $y_S = 1$
- If $y_X$ is undefined but $y_Y$ is defined for some parent$Y$ of $X$ in $T$, set $y_X = y_Y + 1$.
Then $y_X$ is defined iff $X$ occurs in $T$.

Furthermore, an index $y_X$ is defined because $T$ uses a production $Y \to u$ with $|u|_X > 0$ and $y_Y$ is already defined. Hence $(\mathbf x, \mathbf y)$ satisfies $\bigwedge_{X\in V} \beta_X$.

For the converse, suppose that $(\mathbf x, \mathbf y,\mathbf z)$ satisfies
$$\bigwedge_{X\in V} (\alpha_X \land \beta_X) \land \bigwedge_{a\in \Sigma} \gamma_a$$
We represent a production $p = (X\to A_1 \dots A_\ell)$ by a tree.
Consider the following forest containing $x_p$ copies of the production $p$ for each $p\in P$.
The formula $\alpha_X$ with $X \not = S$ states that the number of $X$-roots is equal to the number of $X$-leaves.
The formula $\alpha_S$ states that the number of $S$-roots is equal to the number of $S$-leaves, plus one.

We repeat the following process as longs as possible

- Take a tree $t_1$ with a $X$-leaf and another tree $t_2$ with a $X$-root.
- Replace $t_1$ and $t_2$ by a new tree obtained from $t_1$ where a $X$-leaf is replaced by $t_2$.
Observe that this process does not change the balance between $X$-leaves and $X$-roots.

Also, the number of $a$-leaves $(a\in \Sigma)$ remains unchanged.
The resulting forest has the following properties:
- For each $X$ there exists at most one tree $T_x$ with root $X$. 
- The leaves of $T_s$ are terminals
- The leaves of $T_X (X\not= S)$ are terminals except for one $X$-leaf.
We will further reduce the forest until a single tree remains.

Consider a tree $T$ with root $X$ and leaf $X$. If there exists another tree $T'$ containing an $X$-node, we can insert $T$ into $T'$.
-> This reduces the number of trees by one.

Otherwise, all occurences of $X$ are in $T$. By the formula $\beta_X$, there exists a production $Y\to u$ occurring in $T$ with $|u|_X > 0$ and $y_X = y_Y+1$.
If this occurence of $Y$ lies on the path from the root $X$ to the leaf $X$, we can rearrange the tree as follows.

![](20260313_15h56m49s_grim.png)
-> The index of the root has decreased by one.

Otherwise, we can rearrange the tree as follows:
![](20260313_15h58m18s_grim.png)
-> The index of the root has decreased by one!

Eventually, we obtain a derivation tree for a word $w$ with $|w|_a = z_a$ for all $a\in\Sigma$.

---

A simple corollary:
[Downward closures](Downward%20Closed.md) of context-free languages are computable.

Recall that downwards closures are computable for effective[full trios](Rational%20Transductions.md) iff the [Simulatneous Unboundedness Problem](Simulatneous%20Unboundedness%20Problem.md) is decidable. 
The context-free languages form an effective full trio
(product construction of a PDA with the [Rational transducer](Rational%20Transductions.md)).

Given a context-free grammar $G$ for $L(G) \subseteq a_1^* a_2^* \dots a_n^*$. We can compute a Presburger formula $\varphi(x_1, \dots, x_n)$ for its Parikh image. 
Then $L(G)$ is simultaneously unbounded iff
$$\forall k\exists\mathbf x. \bigwedge_{i=1}^n x_i \ge k \land \varphi(\mathbf x).$$

