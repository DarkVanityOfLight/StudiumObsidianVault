Let $(\Gamma, \gamma_0, \to)$ be a [WSTS](Well-structured%20transition%20systems.md), given a configuration $\gamma \in \Gamma$, is there a $\gamma' \ge \gamma$ with $\gamma_0 \to^* \gamma'$.

## Decidability

>[!DEFINITION]
>Given a subset $S\subseteq\Gamma$, define
>$$pre(S) = \lbrace \gamma\in\Gamma | \exists \gamma' \in S . \gamma\to\gamma'\rbrace$$

>[!LEMMA]
> If $U \subseteq \Gamma$ is [Upwards Closed](Upwards%20Closed.md), then $pre(U)$ is also upwards closed

_Proof:_
Let $\gamma \in pre(U)$ and $\gamma' \ge \gamma$. Then $\gamma \to\delta$ for some $\delta\in U$, by compatibility, there is a $\delta' \in\Gamma$ with $\gamma' \to\delta'$ and $\delta' \ge \delta$, since 
$U$ is upward closed, we know that $\gamma' \in U$. Thus $\gamma' \in pre(U)$

> [!THEOREM]
> Let $W = (\Gamma, \gamma_0, \to, \le)$ be a WSTS such that
> 1. The ordering $\le$ is decidable.
> 2. Given $\gamma\in\Gamma$ one can compute a basis of $pre(\gamma\uparrow)$
> Then the coverability problem for $W$ is decidable


First we observe the following properties

1. Given upward closed sets $U, V \subseteq \Gamma$, we can compute $U \cup V$, for a basis $U_0$ of $U$ and a basis $V_0$ of $V$, take $U_0 \cup V_0$.
2. Given an upward closed set $U \subseteq \Gamma$ and some $\gamma\in\Gamma$, we can decide wehter $\gamma \in U$, given the basis $U_0 = \{\gamma_0, \dots, \gamma_n\}$ of $U$ we check for each $i = 1, 2, \dots, n$ wehter $\gamma_i \le \gamma$, then $\gamma \in U$, else $\gamma \not \in U$
3. Given upward closed sets $U, V \subseteq \Gamma$, we can decide wehter $U \subseteq V$, for a basis $U_0$ of $U$ and a basis $V_0$ of $V$, we have $U \subseteq V$ iff for every $\gamma \in U_0$, there is a $\gamma'\in V_0$ with $\gamma' \le \gamma$.
4. Given an upward closed set $U$, we can compute $pre(U)$, if $U_0 = \{\gamma_1, \dots, \gamma_n\}$ is a basis of $U$, then $$pre(U) = \bigcup_{i=1}^n pre(\gamma_i\uparrow)$$ Since we can compute a basis for each $pre(\gamma_i\uparrow)$ we can compute a basis for $pre(U)$.

Given a subset $S\subseteq \Gamma$, define
$$pre^*(S) = \{\gamma \in\Gamma | \exists \gamma' \in S. \gamma \to^*\gamma'\}$$


Let $S\subseteq \Gamma$ be a subset, then $pre^*(S) = \bigcup_{i\ge 0} pre^i(S)$.

### Abdulla's backward algorithm

```
U <- upclose(gamma)
repeat
	U <- union(U, pre(U))
until pre(U) <= U
return yes if gamma_0 in U else return no
```

This algorithm computes upward closed sets $U_1, U_2, \dots$ with $U_0 = \gamma\uparrow$, by induction $U_i = pre^i(\gamma\uparrow)$. If the algorithm terminates, $U = pre^*(\gamma\uparrow)$ in the end. But it must terminate or otherwise $U_1 \subsetneq U_2 \subsetneq \dots$  would be a strictly ascending chain of upward closed sets.

