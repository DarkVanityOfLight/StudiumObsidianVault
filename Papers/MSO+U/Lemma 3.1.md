
> [!PDF|red] [MSO+U, p.4](MSO+U.pdf#page=4&selection=342,1,368,29&color=red)
> > There is an mso+u formula, which defines the set of words $w\in \lbrace 1, 2, 3\rbrace^\omega$ which have infinitely many 1’s and such that tree(w) has the following properties:
> > - the degree of depth-2 nodes tends to infinity;
> > - all but finitely many nodes of depth 1 have the same degree.



Assume Predicates $P_i/1$ for $i=1,2,3$ such that $P_i(x)$ if the word has character $i$ at position $x$.

---

$$Seg(x, y) := \left(\forall z(u < z < x \to \neg(P_1(z) \lor P_2(z)))\right) \lor \left(\forall z (x < z < u \to \neg(P_1(z) \lor P_2(z)))\right)$$
"There is no $1$ or $2$ between $u$ and $x$"

$$ST(x, y) := \forall z.(x < z < y \to \neg P_1(z))$$
"x, y are in the same tree"


---

> There are infinitely many $1$'s

$$\psi_1 := UX. \forall x(X(x) \to P_1(x))$$
"For every $n$ there is a fininte set $X \subseteq \lbrace x: P_1(x)$ of size $>n$"


As predicate(checking that a set is all ones)
$$isOne(X) := \forall x X(x) \to P_1(x)$$
$$isTwo(X) := \forall x X(x) \to P_2(x)$$
$$isThree(X) := \forall x X(x) \to P_3(x)$$


## The degree of depth 2 nodes tends to infinity

$$\psi_2 := UY. \exists u\left( P_2(u) \land \forall x(Y(x) \to (P_3(x) \land Seg(u, x))) \right)$$
>[!IMPORTANT] Intuition
 > you can find arbitrarily large finite sets $Y$, and for each such $Y$ there is some $u$ of depth 2 whose entire $Y$ consists of 3‑depth children of $u$"

---

## All but finitely many nodes of depth 1 have the same degree

For this we need to say:
> $X$ is an infinite set of depth 1 nodes
$$U X.isOne(X)$$

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
> ([MSO+U, p.5](MSO+U.pdf#page=5&selection=251,0,265,1&color=red))
> one cannot find infinite [alternating sets](Alternating%20Sets.md) $X, Y$ of depth-1 nodes such that infinitely often $\textbf{f}_X$ has strictly bigger dimension than $\textbf{f}_Y$.

> find alternating sets of depth 1 nodes
$$\begin{align}
U X\;U Y.\Bigl(isOne(X)\;\land\;\bigl(isOne(Y)\land Alt(X,Y)\bigr)\Bigr)
\end{align}$$

> ([MSO+U, p.5](MSO+U.pdf#page=5&selection=277,6,297,0&color=red))
> such that there is some $\textbf{g}_X \le \textbf{f}_X$ which is not an [asymptotic mix](Asymptotically%20equivalent.md#Asymptotic%20mix) of any $\textbf{g}_Y \le \textbf{f}_Y$

> $g_x$ is a choice of depth 3 descendants of $X$
$$$$