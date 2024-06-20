

## Axioms
We have the same axioms as in the [Theory of equality](Theory%20of%20equality.md), additionally we have the functional and relational congruence:

$$\forall \overline x,\overline y \left(\bigwedge^n_{i=1} x_i = y_i\right) \to f(\overline x) = f(\overline y)$$
$$\forall \overline x, \overline y \left( \bigwedge^n_{i=1} x_i = y_i\right) \to R(\overline x) \leftrightarrow R(\overline y)$$
---

>[!THEOREM]
>Deciding whether a conjunctive formula $\varphi$ is EUF-satisfiable in is polynomial-time solvable.

>[!COROLLARY] 
> Deciding satisfiability of a quantifier free formula $\varphi$ in EUF is in NP


## Removing predicates

Each $k-ary$ predicate $R$ can be "simulated" by a $k$-ary function $f$
$$a\in R \iff f(\overline a) = \cdot$$


We introduce a new constant symbol $\cdot$. For each $k$ary predicate symbol $R$, we create a new $k$ary function $f_R$ symbol.
And define the following substitution $\sigma : R(\overline x) \mapsto (f_R(\overline x) = \cdot)$

>[!PROPOSITION]
>Let $\varphi$ be a formula in EUF. Then, $\varphi$ and $\varphi[\sigma]$ are equisatisfiable.

## Subterms

Given a term $t$, the set $sub(t)$ of subterms of $t$ is defined inductively:

_Base case:_
$sub(c) = \lbrace c\rbrace$ for a $0$ary function symbol $c$

_Induction:_
$sub(f(t_1, \dots, t_r)) = \lbrace f(t_1, \dots, t_r)\rbrace \cup \bigcup^r_{i=1} sub(t_i)$

Given a formula $\varphi$, the set $sub(\varphi)$ denotes the set of all subterms in $\varphi$.

## Solving EUF

_Input:_ A formula $\varphi$ in EUF

1. Put each term $t\in sub(\varphi)$ in a separate equivalence class
2. Repeat the following rule till it cannot be applied: If $t_1 = t_2$ appears as a conjunct in $\varphi$, then merge equivalence classes for $t_1$ and $t_2$
3. Repeat the following rule till cannot be applied: If $t_1$ and $t_2$ appear in the same equivalence class, and $f(t_1)$ and $f(t_2)$ appear in $\varphi$, then merge equivalence classes for $f(t_1)$ and $f(t_2)$
4. If some $t_1 \not = t_2$ occurs in $\varphi$ but $t_1$ and $t_2$ belong to the same class, then return UNSAT; otherwise, return SAT

>[!COROLLARY]
>A quantifier free formula $\varphi$ is EUF-satisfiable iff it has a [Herbrand-Modell](Herbrand-Modell)




