
A subset $S \subseteq X$ is (upward) directed if for every $x, y \in S$, there exists $z\in S$ with $x \le z$ and $y\le z$. 

A non-empty subset $I\subseteq X$ is an _ideal_ if:
1. $I$ is [Downward Closed](Downward%20Closed.md) 
2. $I$ is upward directed


## Maximal Ideals

Let $D \subseteq X$ be downward close. An ideal $I \subseteq D$ is called _maximal_ in $D$ if for every ideal $J$ with $I \subseteq J\subseteq D$, we have $I = J$.

For every downward closed set $D\subseteq X$, we can write 
$D = I_1 \cup \dots \cup I_n$ where $I_1, \dots, I_n$ are exactly the maximal ideals in $D$. This decomposition is unique up to reordering.


By [Ideal Decomposition](Ideal%20Decomposition.md) we know that we can decompose $D = J_1 \cup \dots \cup J_m$ for some ideals $J_1, \dots, J_m$. Of these ideals we pick those that are maximal. we keep $J_i$ if there is no $J_k$ with $J_i \subsetneq J_k$. Let the picked set of ideals be $I_1, \dots, I_n$. 
These are exactly the maximal ideals in $D$.

- $D = I_1\cup \dots\cup I_n$. Let $x\in D$, then there is some ideal $J_i$ with $x \in J_i$, if $J_i$ is maximal we are done, if not there is a $I_j$ with $J_i \subseteq I_j$, and thus $x \in I_j$ 
2. Suppose $I_i \subseteq J$, where $J$ is an ideal with $J\subseteq D$, then $J = J_i$, since $D = \bigcup_{k=1}^m I_k$ we have $$J = \bigcup_{k=1}^m (J \cap J_k).$$ Each $J \cap J_k$ is downward closed. Because $J$ is upward directed, there exists $k$ such that $J\subseteq J_k$, Since $J_i \subseteq J$, we get $J_i \subseteq J_k$, but $J_i$ and $J_k$ are maximal among the $I_j$, so this implies $J_i = J_k$, thus $J = J_i$ and therefore $J_i$ is maximal in $D$
3. Let $I$ be a maximal ideal of $D$. Since $D = J_1 \cup \dots \cup J_n$ and $I$ is directed $I \subseteq J_k$ for some $k$. Because $J_k\subseteq D$ and $I$ is maximal in $D$, $I = J_k$. If $J_k$ were not maximal, then there would exist $J_\ell$ with $J_k \subsetneq J_\ell$, then $I = J_k \subsetneq J_\ell \subseteq D$ contradicting maximiality of $J$.

## Ideals in $\mathbb N^k$
The ideals in $\mathbb N^k$ are exactly the sets of the form $Idl(\mathbf u)$ of $\mathbf u\in \mathbb N^k_\omega$.

Clearly every $Idl(\mathbf u)$ for $\mathbf u\in\mathbb N^k_\omega$ is an ideal. They are clearly downward closed.
For upward directness consider $\mathbf v', \mathbf v''\in Idl(\mathbf u)$. We construct $\mathbf v \in Idl(\mathbf u)$, $\mathbf v = (v_1, \dots, v_k)$, with $\mathbf v' \le \mathbf v$ and $\mathbf v'' \le \mathbf v$. For each component we take the maximum of $\mathbf v'$ and $\mathbf v''$.

Every ideal is of the form $Idl(\mathbf u)$, consider $I \subseteq \mathbf N^k$, then by [Ideal <=> Downclosure](Ideal%20<=>%20Downclosure.md) there is a sequence $\mathbf{v}_1 \le \mathbf{v}_2 \le\dots \in I$ such that $I = \{\mathbf v_1, \mathbf v_2, \dots\}\downarrow$. For $i=1, ..., k$ construct $\mathbf u \in\mathbb N^k$ $\mathbf u = (u_1, ..., u_)$ as follows.
- If the $i$-th component of $\mathbf{v}_1 \le \mathbf{v}_2 \le\dots$ is unbounded set $u_i = \omega$
- If there is a maximum value $m\in\mathbb N$ set $u_i = m$.


## Ideals in $\Sigma^*$
Let $\Sigma$ be an [Alphabet](Alphabet.md).
The ideals of $(\Sigma^*, \preceq)$ are made of 
- An atom is either
	- A Set $\{a, \varepsilon\}$ with some $a\in\Sigma$
	- $\Delta^*$ for some $\Delta \subseteq \Sigma$
- A product is a concatenation $A_1\dots A_n$, where each $A_i$ is an atom.


It is easy to see that every product is an ideal.

We will show that every ideal is a product.

> An [NFA](Nichtdeterministische%20endliche%20Automaten.md) $(Q, \Sigma, T, q_0, F)$ is called partially ordered if there is a partial order $(Q, \le)$ such that for every transition $(p, a, q)\in T$, we have $p \le q$.

> If $D\subseteq \Sigma^*$ is downward closed, then there is a paritally ordered NFA $\mathcal A$ with $L(\mathcal A) = D$


Let $D\subseteq \Sigma^*$ be the downward closed and non-empty, then there are
$\{w_1,\dots,w_n\}$ such that $D = \Sigma^* \setminus \{w_1, \dots, w_n\}\uparrow$. We construct the NFA $\mathcal A$ as follows
- $Q := P_1 \times \dots \times P_n, P_i = \{ w\in\Sigma^* | w \text{is a prefix of } w_i \}$
- $q_0 = (\varepsilon, \dots, \varepsilon)$
- For $q = (p_1, \dots, p_n)\in Q$ and $a\in\Sigma$, introduce transition $(q, a, q')$, where $q' = (p_1', \dots, p'_n)$ such that for each $i = 1, \dots, n$: $$p_i' = \begin{cases}p_i a & \text{if $p_i a$ is a prefix of $w_i$} \\ p_i &\text{otherwise}\end{cases}$$If $q_0 \to^w (p_1, \dots, p_n)$, then for each $i: p_i$ is the longest prefix $p$ of $w_i$ such that $p \preceq w$.
- $F = \{p_1, \dots, p_n\in Q | |p_i| < |w_i| \forall i\}$

It holds that $L(\mathcal A) =  D$, as a partial order we choose
$$(p_1, \dots, p_n) \le (p_1', \dots, p'_n) \iff \text{$p_i$ is a prefix of $p_i'$ for every $i$}$$


> Let $\mathcal A = (Q, \Sigma, T, q_0, F)$ be a partially ordered NFA. Then $L(\mathcal A)$ is a finite union of sets of the form $Y_0^* x_1 Y_1^* x_2 Y_2^* \dots x_n Y_n^*$ for letters $x_1, \dots, x_n\in\Sigma$ and alphabets $Y_0, \dots, Y_n\subseteq \Sigma$

Let $(Q,\le)$ be the partial order. By induction on $|Q|$:
We can assume that $q_0$ is minimal w.r.t. $\le$. Let $(q_0, a_1, q_0), \dots, (q_0, a_\ell, q_0)$ be the self-loops in $q_0$. Let $(q_0, b_1, r_1), \dots, (q_0, b_m, r_m)$ be the transitions starting in $q_0$ that are not self-loops.
For $i = 1, ..., m$, let $\mathcal A_i$ be the automaton obtained from $\mathcal A$ by removing $q_0$ and making $r_i$ initial. Then $\mathcal A_i$ is again partially ordered and has $k$ states. By induction $L(\mathcal A_i)$ is a finite union $L(\mathcal A_i) = \bigcup_{j=1}^{s_i} K_{i, j}$ of languages $K_{i, j}$ as above. 
$$L(\mathcal A) = \bigcup^m_{i=1} Y^* b_i L(\mathcal A_i) = \bigcup^m_{i=1} \bigcup^{s_i}_{j=1} Y^* b_i K_{i, j} \quad Y = \{a_1, \dots, a_\ell\}$$
If $q_0 \in F$ then we have to add $Y^*$ to this union.


We can now prove the main theorem.
It remains to show that every ideal is a product.

Let $I \subseteq \Sigma^*$ be an ideal. Since $I$ is downward closed, we can apply the first lemma, so we know that $I = L(\mathcal A)$ for some partially ordered NFA $\mathcal A$. Then by the second lemma we have
$$I = L(\mathcal A) = \bigcup^m_{i=1} Y^*_{i, 0} x_{i, 1} Y_{i, 1}^* \dots x_{i, s} Y_{i, {s_i}}^*$$
for some letters $x_{i, j} \in\Sigma$ and alphabets $Y_{i, j} \subseteq \Sigma$. Since $I$ is downward closed, we have

$$I = I\downarrow = \bigcup^m_{i=1} Y^*_{i, 0} \{x_{i, 1}, \varepsilon\} Y_{i, 1}^* \dots \{x_{i, s}, \varepsilon\} Y_{i, {s_i}}^*$$

Since $I$ is an ideal, we have $I\subseteq Y_{i, 0}^* \{x_{i, 1},\varepsilon\} Y_{i, 1}^* \dots \{ x_{i, s_i},\varepsilon \} Y_{i, s_i}^*$ for some $i$. But then $I =  Y_{i, 0}^* \{x_{i, 1},\varepsilon\} Y_{i, 1}^* \dots \{ x_{i, s_i},\varepsilon \} Y_{i, s_i}^*$
