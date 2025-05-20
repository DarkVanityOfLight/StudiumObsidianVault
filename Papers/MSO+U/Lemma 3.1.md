
> [!PDF|red] [MSO+U, p.4](MSO+U.pdf#page=4&selection=342,1,368,29&color=red)
> > There is an mso+u formula, which defines the set of words $w\in \lbrace 1, 2, 3\rbrace^\omega$ which have infinitely many 1’s and such that tree(w) has the following properties:
> > - the degree of depth-2 nodes tends to infinity;
> > - all but finitely many nodes of depth 1 have the same degree.



Assume Predicates $P_i/1$ for $i=1,2,3$ such that $P_i(x)$ if the word has character $i$ at position $x$.

---

$$Seg(x, y) := \left(\forall z(u < z < x \to \neg(P_1(z) \lor P_2(z)))\right) \lor \left(\forall z (x < z < u \to \neg(P_1(z) \lor P_2(z)))\right)$$
"There is no $1$ or $2$ between $u$ and $x$"

---

> There are infinitely many $1$'s

$$\psi_1 := UX. \forall x(X(x) \to P_1(x))$$
"For every $n$ there is a fininte set $X \subseteq \lbrace x: P_1(x)$ of size $>n$"

---
> The degree of depth 2 nodes tends to infinity

$$\psi_2 := UY. \exists u\left( P_2(u) \land \forall x(Y(x) \to (P_3(x) \land Seg(u, x))) \right)$$
"you can find arbitrarily large finite sets $Y$, and for each such $Y$ there is some $u$ of depth 2 whose entire $Y$ consists of 3‑depth children of $u$"

---
> All but finitely many nodes of depth 1 have the same degree



