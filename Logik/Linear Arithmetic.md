
Let's look at the theory $(\mathbb Q; <, +, 0,1)$ for convenience, we allow constant symbols $c\quad(c\in \mathbb Q)$ to be interpreted as itself and unary function symbols $c\cdot\quad(c\in\mathbb Q)$ interpreted as multiplication by this coefficient:
$$c\cdot : n\mapsto c\cdot n$$
We call the resulting theory $Th(\mathcal Q_+)$.

>[!THEOREM]
>$Th(\mathcal Q_+)$ admits [quantifier Elemination](Quantorenelemination.md), and is therefore [[complete]] and [decidable](Entscheidbar.md)

## Normal Forms for Atoms

We allow general linear (in)equalities as atoms
$$t_1 \sim t_2, \qquad \sim\in\lbrace <, >, =\rbrace$$
where each side is of the form
$$c_1 x_1 + \dots c_n x_n + c_0$$
where the variables $x_i$'s are pairwise distinct.
Each such atom can be simplified further to
$$t\sim 0, \qquad\sim\in\lbrace <, >, =\rbrace$$
### Solved Forms
An atom is in solved form for a variable $x$ if it's of form:
$$x\sim t, \qquad \sim\in\lbrace <,>, =\rbrace$$
and $x$ doesn't appear in $t$.

When eliminating $x$, we will assume each atom is in solved form for $x$.

## Fourier Motzkin Elimination

We show how to eliminate $x$ from $\exists x\varphi$, where
$$\varphi = \bigwedge^n_{i=1} x \sim_i t_i; \qquad \sim_i\in\lbrace <, >, =\rbrace$$

1. One conjunct is $x=t$. Use: $$\mathcal Q_+ \vDash \exists x\varphi \leftrightarrow \varphi[t/x]$$
2. Separate conjuncts into lower/upper bounds for $x$ $$\mathcal Q+ \vDash \exists x\left(\bigwedge^r_{i=1} l_i < x \land \bigwedge^s_{j=1} x < u_j\right) \leftrightarrow \bigwedge^r_{i=1}\bigwedge^s_{j=1} l_i < u_j$$
3. 