
Let $A = \langle V, E\rangle$ be an [arena](Arena.md), $U \subseteq V$, and $i \in \lbrace 0, 1\rbrace$.

## Controlled predecessor

The controlled predecessor for Player $i$ on $U$ is.

$$\text{CPre}_i (U) := \lbrace v \in V_i | \text{suc}(v) \cap U \not = \emptyset\rbrace \cup \lbrace v\in V_{1-i} | \text{suc}(v) \subseteq U\rbrace$$

> [!TIP] Intuition
The controlled predecessor tells us which vertices are "one step away" from reaching $U$, either because Player $i$ can force a move to $U$, or because Player $1-i$ has no choice but to move into $U$.

## $i$ Attractor

The $i$-attractor $Attr_i(U)$ is defined inductively by applying the controlled predecessor
- $Attr_i^0(U) := U$
- $Attr^{n+1}_i (U) := Attr^n_i(U) \cup CPre_i(Attr^n_i(U))$ and
- $Attr_i(U) := \bigcup_{n\in\mathbb N} Attr^n_i(U)$
- 
By monotonicity of the attractor, there exists $k \le |V|$ such that $Attr_i^k(U) = Attr^{k+1}_i(U)$.

> [!TIP] Intuition
> The attractor $Attr_i(U)$ is the "capture zone" for Player $i$, meaning the set of vertices from which Player $i$ can always force the game into $U$. This includes not just vertices that can reach $U$ directly, but also those that can reach $U$ after several moves, no matter how the opponent plays


