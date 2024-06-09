
>[!THEOREM]
>The theory $Th(\mathbb Z; +, <, =, 0, 1)$ is decidable.

This was proven by [quantifier elimination](Quantorenelemination.md)

## Quantifier Free Linear Arithmetic

>[!THEOREM]
>The existential theories of $Th(\mathbb Z; + , <, =, 0, 1)$ and $Th(\mathbb R; +, <, =, 0, 1)$ are both [[NP-complete]].

## Quantifier Elimination

1. We allow constant symbols $c\quad (c\in\mathbb Z)$ interpreted as itself
2. Unary function symbols $c\cdot\quad (c\in\mathbb Z)$- scalar multiplication

Furthermore, we also add the binary relation symbol $\equiv_k,\quad (k\in\lbrace 2, 3,\dots\rbrace)$:
$$a \equiv_k b \quad\iff a = b + kc\text{ for some $c\in\mathbb Z$}$$
So, $\equiv_k$ is interpreted as congruence modulo $k$.
The resulting theory is referred as $Th(\mathcal Z_+)$

### Chinese Remainder Theorem
[Chinesischer Restsatz](Chinesischer%20Restsatz.md)

>[!THEOREM]
>$\mathcal Z_+ \vDash x \equiv_{m_1} n_1 \land\dots\land x \sim_{m_k} n_k$ whenever $\gcd(m_i, m_j) | n_i -n_j$ for all $i\not= j$. The solution is unique modulo $lcm(m_1, \dots, m_k)$.

>[!COROLLARY]
>If $x \equiv_{m_1} c_1 \land \dots \land x \sim_{m_k} c_k$ is $\mathcal Z_+$ satisfiable, then there is a solution $x_0$ in $[0, lcm[m_1, \dots, m_k] -1]$

### Normal Forms for Atoms

We allow general linear (in)equalities as atoms
$$t_1\sim t_2 \qquad \sim\in\lbrace <, >, =, \equiv_k \rbrace$$
where each side is of the form
$$c_1 x_1 + \dots + c_n x_n + c_0$$
where the variables $x_i$'s are pairwise distinct.
Each such atom can be simplified further to
$t_1 \sim 0, \quad\sim\in\lbrace <, >, =, \equiv_k\rbrace$
Each negative literal can be turned into a positive one.
$$\neg(t_1 \sim 0)\quad \sim\in\lbrace <, >, =, \equiv_k\rbrace$$
For example
$$\mathcal Z_+ \vDash \neg(x \equiv_3 1) \iff \mathcal Z_+ \vDash x \equiv_3 = 0 \lor x \equiv_3 = 1\lor x \equiv_3 = 2$$
### Semi solved Forms
An atom  is in semi solved form for a variable $x$ if it's of form
$$cx \sim t, \quad \sim\in\lbrace <, >, =, \equiv_k\rbrace$$
and $x$ doesn't appear in $t$

### Solved Forms
An atom is in solved form for a variable $x$ if it's of form
$$x \sim t,\quad \sim\in\lbrace <, >, =, \equiv_k\rbrace$$
and $x$ doesn't appear in $t$

### Semi Solved to Solved
We can archive Solved form by normalizing the coefficients.
We assume a conjunction of atoms in the quantifier-free part:
$$\psi := \exists x(\alpha_1 \land \dots\land \alpha_m) \quad c_i := \text{coef of $x$ in $\alpha_i$}$$
Let $p = lcm(c_1, \dots, c_m)$
Multiply the l.h.s/r.h.s/moduli of the $i$th (in)equations/congruence by $p/c_i$

>[!NOTE]
>For congruence, we need to multiply the moduli by $p/c_i$ too.

We introduce a new variable $x'$ to replace $px$ and add conjunct $x' \equiv_p 0$
#### Example
$$\begin{align}
\psi &:= \exists x(z < 2x \land 3x < y \land 4x \equiv_3 1)\\
\psi' &:= \exists x(6z < 12x \land 12x < 4y \land 12x \equiv_9 3)\\
\psi'' &:= \exists x'(6z < x' \land x' < 4y \land x' \equiv_9 3 \land x' \equiv_{12} 0)
\end{align}$$

### Variable Elimination

We show how to eliminat $x$ \from $\exists x\varphi$ where
$$\varphi = \bigwedge^n_{i=1} x\sim_i t_i\quad \sim_i \in\lbrace <, >, =, \equiv_k \rbrace$$
1. One conjunct is $x = t$. Use: $$\mathcal Z_+ \vDash \exists x\varphi \leftrightarrow \varphi[t/x]$$
2. No equalities/congruences. Separate conjuncts into lower/upper bounds for $x$ $$\mathcal Z_+ \vDash\exists x \left(\bigwedge^r_{i=1} l_i < x \land \bigwedge^s_{j=1} x < u_j\right) \leftrightarrow \bigwedge^r_{i=1}\bigwedge^s_{j=1} l_i + 1 < u_j$$
3. No equalities, but some congruences and _lower_ bounds $$\psi(\overline y) := \exists x\left(\bigwedge^r_{i=1} l_i < x \land \bigwedge^s_{j=1} x< u_j \land \bigwedge^h_{i=1} x\equiv_{k_i} t_i\right)$$
   Let $M = lcm(k_1, \dots, k_h)$
   For any valuation $\nu : \overline y \to \mathcal Z$, let $L_\nu = \max\lbrace l_i\rbrace$ and $U_\nu = \inf\lbrace u_i\rbrace$
   For $\varphi[\nu]$ to be set. it suffices to restrict $x\in (L_\nu, L_\nu + M] \cap (L_\nu, U_\nu)$. Thus $$\mathcal Z_+ \vDash \psi(\overline y) \leftrightarrow \bigvee^r_{p=1}\bigvee^M_{q=1}\left(\bigwedge^r_{i=1} l_i < l_p + q \land \bigwedge^s_{j=1} l_p + q < u_j \bigwedge^h_{i=1} l_p + q \equiv_{k_i} t_i\right)$$
4. No equalites/lower bounds but some congruences $$\psi(\overline y) := \exists x\left(\bigwedge^s_{j=1} x < u_j \land \bigwedge^h_{i=1} x \equiv_{k_i} t_i\right)$$


## Expressiveness
>[!THEOREM]
>Every $\mathcal Z_+$-definable [set](Mengen.md) $S\subseteq\mathbb Z$ is expressible as a finite [union](Vereinigung%20von%20zwei%20Mengen.md) of [Arithmetic Progression](Arithmetic%20Progression.md).
