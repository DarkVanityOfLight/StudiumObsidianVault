
> [!PDF|red] [MSO+U, p.4](MSO+U.pdf#page=4&selection=342,1,368,29&color=red)
> > There is an mso+u formula, which defines the set of words $w\in \lbrace 1, 2, 3\rbrace^\omega$ which have infinitely many 1’s and such that tree(w) has the following properties:
> > - the degree of depth-2 nodes tends to infinity;
> > - all but finitely many nodes of depth 1 have the same degree.



Assume Predicates $P_i/1$ for $i=1,2,3$ such that $P_i(x)$ if the word has character $i$ at position $x$.

---
> Set $X$ is a subset or equal to $Y$
$$Subseteq(X, Y) := \forall x.(X(x) \to Y(x))$$
We also write $X \subseteq Y$


> Nodes $x, y$ are in the same segment
$$Seg(x, y) := \left(\forall z(u < z < x \to \neg(P_1(z) \lor P_2(z)))\right) \lor \left(\forall z (x < z < u \to \neg(P_1(z) \lor P_2(z)))\right)$$

> Nodes $x, y$ are in the same tree
$$ST(x, y) := \forall z.(x < z < y \to \neg P_1(z))$$

> Set $X$ has only depth $i$ nodes
$$isOne(X) := \forall x X(x) \to P_1(x)$$
$$isTwo(X) := \forall x X(x) \to P_2(x)$$
$$isThree(X) := \forall x X(x) \to P_3(x)$$
> Set $X$ is infinite
$$Infinite(X) := \neg U Z. Z \subseteq X$$


---

## There are infinitely many 1's

$$\psi_1 := \exists X. Infinite(X) \land \forall x. X(x) \to P_1(x)$$


## The degree of depth 2 nodes tends to infinity

$$\psi_2 := UY. \exists u\left( P_2(u) \land \forall x(Y(x) \to (P_3(x) \land Seg(u, x))) \right)$$
>[!IMPORTANT] Intuition
 > you can find arbitrarily large finite sets $Y$, and for each such $Y$ there is some $u$ of depth 2 whose entire $Y$ consists of 3‑depth children of $u$"

#fixme

---


## All but finitely many nodes of depth 1 have the same degree

For this we need to say:
> $X$ is an infinite set of depth 1 nodes
$$\exists X. Infinite(X) \land isOne(X)$$

> Depth 1 nodes have bounded degree

Define $X$ have bounded degree (assuming $X$ is only depth 1 nodes):
$$\phi(X) := \neg UY.\left( isTwo(Y) \land \exists x.(X(x) \land  \forall y.(Y(y) \to ST(u, y)) ) \right)$$

>[!IMPORTANT] Intuition
> There is no unbounded set $Y$ such that all $y\in Y$ are depth 2 nodes and no tree $x\in X$ contains all $y\in Y$

Then:
$$U X (\forall x(X(x) \to P_1(x)) \land \phi(X))$$

>[!IMPORTANT] Intuition
>There is an infinite set of depth 1 nodes and they are of bounded degree

---

> [!PDF|red] [MSO+U, p.5](MSO+U.pdf#page=5&selection=272,31,297,1&color=red)
> > one cannot find infinite [alternating sets](Alternating%20Sets.md) $X, Y$ of depth-1 nodes such that there is some $\textbf{g}_X \le \textbf{f}_X$ which is not an asymptotic mix of any  $\textbf{g}_Y \le \textbf{f}_Y$ .
> 


![Alternating Sets](Alternating%20Sets.md)

> $F$ selecst some depth 3 descendants of $X$ ($F \le f_X$)
$$Sel_3(F, X) := \forall u F(u) \to P_3(u) \land \exists v (X(v) \land Ancestor(v, u))$$

>[!IMPORTANT] FIXME
>Define Ancestor
> #fixme


> $F$ is bounded on $H$
$$Bounded(F, H) := \neg U Z (Z \subseteq H \land \exists u(Z(u) \land F(u)))$$

> Every $F$ trace is asymptotically equivalent to some $G$-trace
$$\forall H.[\forall u (H(u) \to P_3(u)) \to Bounded(F, H) \leftrightarrow Bounded(G, H)]$$

$$\begin{align}
\neg \exists X, Y.& Infinite(X) \land Infinite(Y)\land Alternating(X, Y)\\
\land \exists F.& Sel_3(G, Y) \to \forall G. (Sel_3(G, Y) \to \neg AsMix(F, G))
\end{align}$$

