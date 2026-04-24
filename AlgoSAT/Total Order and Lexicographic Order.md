---
aliases:
  - Lex-leader symmetry breaking
---

Let $Var(F)$ be the [set](Mengen.md) of [variables](Variable.md) of $F$.

A _total order_ ([Totalordnung](Totalordnung.md)) $\prec$ on $Var(F)$ is a linear ordering of the varibales. We write
$$v_1 \prec v_2 \prec \dots \prec v_n$$
for the sequence of variables sorted according to $\prec$.


Every complete [assignment](Assignment.md) $\tau$ induces a Boolean vector, where the ordering of variables is given by $\prec$. Given two assignments $\tau$ and $\tau'$, we define $\tau \le_{lex}^{\prec} \tau'$ iff $\tau = \tau'$, or there exists an index $i$ such that

$$\tau(v_j) = \tau'(v_j) \text{ for all } j < i \text{ and } \tau(v_i) < \tau'(v_i)$$
This defines a total order on the set of complete assignments.


The idea of _lex-leader symmetry breaking_([Static Symmetry Breaking](Static%20Symmetry%20Breaking.md)) is to add clauses that falsify non-lex-leader assignments.

For some total ordering $\prec$ of variables and [Symmetry](Symmetry.md) $\varphi$ of $F$, we encode that
$$\tau\le^\prec_{lex} \varphi(\tau)$$
for all complete assignments $\tau$ must hold.

## Encoding
Let $x_1 \prec \dots \prec x_n$, for every $i\in\{1, \dots, n\}$ and every vector $(a_1, \dots, a_{i-1})\in \{0, 1\}^{i-1}$ add
$$(\overline x_i \lor y_i \lor p_{1, a_1} \lor \dots \lor p_{i-1, a_{i-1}})$$ where for $j < i$
$$p_{j, a} = \begin{cases}
x_j \lor y_j & a = 0\\
\overline x_j \lor y_j & a = 1
\end{cases}$$

We ensure the first difference is at position $i$ and then impose $x_i \le y_i$.

This encoding gives $\Omega(2^n - 1)$ clauses.

Using auxiliary variables we can do the following:
- $x_1 \le y_1$
- $e_1 \iff x_1 = y_1$
- $e_{i-1} \implies x_i \le y_i$ with $i\in[2, n-1]$
- $e_i \iff e_{i-1} \land x_i = y_i$ with $i\in[2, n]$
Here $e_i$ expresses that prefixes up to position $i$ are equal.

## Correctness

Let $\Gamma$ be a subgroup of the [Semantic Symmetries](Semantic%20Symmetry.md) of $F$ and fix a total order $\prec$ on $Var(F$). Let's say $LL_\Gamma$ encodes all lex-leader constraints
$$LL_\Gamma : \forall\varphi \in\Gamma, \tau\le^\prec_{lex} \varphi(\tau)$$

> $F$ and $LL_\Gamma$ are equisatisfiable

Let $\tau$ be any satisfying assignment of $F$. Consider its [Orbit](Orbit.md) $O := \{\varphi(\tau) | \varphi\in \Gamma\}$. The order $\le^\prec_{lex}$ is a total order on assignments, hence $O$ has a lexicographic-ally smallest element call it $\tau^*$. By definition of $O$, there exists $\psi\in\Gamma$ such that $\tau^* = \psi(\tau)$. Because $\psi$ is a semantic symmetry, satisfiability is preserved
$$F[\tau] = true \implies F[\psi(\tau)] = F[\tau^*] = true$$
It remains to show that $\tau^*$ satisfies $LL_\Gamma$. For any $\varphi\in\Gamma$, we have $\varphi(\tau^*) \in O$ and since $\tau^*$ is the $\le^\prec_{lex}$-minimum element of $O$, $\tau^* \le^\prec_{lex} \varphi(\tau^*)$. Hence $\tau^* \vDash LL_\Gamma$.

