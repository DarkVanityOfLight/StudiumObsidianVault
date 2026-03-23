
> Given a [language](Sprache.md) $K\in \mathcal C$, $K\subseteq a_1^*a_2^* \dots a_n^*$ where each $a_i$ is a letter, is the [Downward Closure](Downward%20Closed.md) $K\downarrow = a_1^*a_2^*\dots a^*_n$?

The name comes from the fact that $K\downarrow = a_1^* a_2^* \dots a_n^*$ iff for any $k\in\mathbb N$, there exists a word $a_1^{x_1} a_2^{x_2} \dots a_n^{x_n}\in K$ such that each $x_i \ge k$.

> For any effective [full trio](Rational%20Transductions.md) $\mathcal C$, the following two statements are equivalent:
> 1. From $K\in\mathcal C$, we can compute an [NFA](Nichtdeterministische%20endliche%20Automaten.md) accepting $K\downarrow$
> 2. SUP is decidable for $\mathcal C$

$(1) \implies (2)$
We know the [down closure](Downward%20Closed.md) of $K$ is computeable, thus we can take the NFA produced and check if $L(\mathcal A) = a_1^* a_2^* \dots a_n^*$.

$(2) \implies (1)$

We first show that the emptiness problem can be reduced to SUP.
For this we construct a [rational transducer](Rational%20Transductions.md) $T$ with $L(T) = \Sigma^* \times \{a\}^*$, by assumption, $TK$ can be computed and is a subset of $a^*$. Now 
$$K = \emptyset \iff TK \not = a^*$$


Now let $K$ be a language of class $\mathcal C$, the language $K\downarrow$ is described by a finite union of products UOP as we have seen in [Ideal <=> Downclosure](Ideal%20<=>%20Downclosure.md). We can check for each UOP $r$, wheter $L(r) = K\downarrow$, until we find the correct $r$. Since $\Sigma$ is finite, there are only finitely many products of the form $\Sigma_0^* a_1 \Sigma_1^* \cdots a_k \Sigma_k^*$ with $k \le |\Sigma|$, and therefore only finitely many finite unions of such products (UOPs); hence we can enumerate all candidates $r$.

We now check if $K\downarrow \subseteq L(r)$ and $L(r) \subseteq K\downarrow$, by checking emptiness:


$K\downarrow \subseteq L(r)$
![](Simulatneous%20Unboundedness%20Problem%202026-03-10%2015.37.24.excalidraw)

We have $L(T) = \{(u, v) | v \preceq u\}$, then $TK = K \downarrow$. Since $\Sigma^*\setminus L(r)$ is regular, the language $K\downarrow \cap (\Sigma^*\setminus L(r))$ is also in $\mathcal C$ by [Nivat's Theorem](Nivat's%20Theorem.md). Since the emptiness problem is decidable for $\mathcal C$, we can check $K\downarrow \cap (\Sigma^* \setminus L(r)) = \emptyset$ wich is equivalent to $K\downarrow \subseteq L(r)$.


$L(r) \subseteq K\downarrow$
$L(r)$ is a finite union of languages of the form
$$\{w_0\}\downarrow Y_1^* \{w_1\}\downarrow Y_2^* \dots Y_n^* \{w_n\}\downarrow$$
We check if each of these is a subset of $K\downarrow$

To decide the inclusion, we observe the following:
Let $\Gamma = y_1, y_2, \dots, y_n\subseteq\Sigma$ and $L\subseteq \Sigma^*$ be downward closed. Then $\Gamma^* \subseteq L$ iff for each $k\in\mathbb N$  there is $\ell \ge k$ with $(y_1y_2\dots y_n)^\ell \in L$.

Let $u_i = y_1y_2\dots y_m$, where $Y_i = \{y_1, y_2,\dots, y_m\}$.
Due to the observation it suffices to check whether for any $k\in\mathbb N$, there are numbers $x_1, x_2, \dots, x_n\in\mathbb N$ with each $x_i \ge k$ such that
$$w_0 u_1^{x_1} w_1 u_2^{x_2} w_2 \dots u_n^{x_n} w_n \in K\downarrow$$

We define a transducer $T$ with
$$L(T) := \{ (w_0, u_1^{x_1} w_1 u_2^{x_2} w_2\dots u_n^{x_n}, a_1^{x_1} a_2^{x_2} \dots a_n^{x_n}) | \forall i x_i \ge 0 \}$$

The following properties hold:
$$T(K\downarrow) = \{ a_1^{x_1} a_2^{x_2} \dots a_n^{x_n} | w_0 u_1^{x_1} w_1 u_2^{x_2} w_2 \dots u_n^{x_n} w_n \in K\downarrow \}$$
$$T(K\downarrow)\downarrow = a_1^* a_2^* \dots a_n^* \iff w_0 Y_1^* w_1 Y_2^* w_2 \dots Y_n^* w_n \subseteq K\downarrow$$

Since SUP is decidable for $\mathcal C$, we can decide $T(K\downarrow)\downarrow =  a_1^* a_2^* \dots a_n^*$ and therefore $w_0 Y_1^* w_1 Y_2^* w_2 \dots Y_n^* w_n \subseteq K\downarrow$.

