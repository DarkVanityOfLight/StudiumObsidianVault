$$\begin{align}
&\exists^{ramsey} \textbf{x}, \textbf{y}.( r^\top \textbf{x} = s^\top \textbf{y} + t^\top \textbf z + h) \\\iff& \exists x_0, x. (r^\top x = 0 \land s^\top x = 0 \land r^\top x_0 = s^\top x_0 + t^\top z + h \land x \not = 0)
\end{align}$$

---

## Proof
### Infinite clique => AP

Suppose we have an infinite set
$$S = \lbrace x_1, x_2, x_3, \dots\rbrace \subseteq \mathbb Z^d$$
and two fixed vectors $r, s\in \mathbb Z^d$ and some constant $C = t^\top z + h$. We assume that any pair $(x, y) \in S\times S$ with $x \not = y$ satisfies the clique condition:
$$r^\top x = s^\top xy + C$$
Our goal is to find integer vectors $v\not = 0, w$ such that
$$r^\top v = 0\qquad s^\top v = 0\qquad r^\top w = s^\top w + C \qquad v \not = 0$$
These vectors will witness the infinite AP
$$\lbrace w + nv : n \in \mathbb Z\rbrace$$
contained in $S$.

---
Let's turn our attention to finding the vector $v$.

First notice that because of $r^\top v = 0$ and $s^\top v = 0$ such a $v$ must lie in the intersection of the two kernels $v \in ker(r^\top) \cap ker(s^\top)$

Next we claim that all differences of distinct elements $x,y \in S$ must lie in the intersection of the kernels:

For this first fix some $y$, and vary $x$:
$$\begin{align}
&r^\top x = \underbrace{s^\top y}_{\text{const }\alpha} + C\\
&r^\top x = \alpha + C&(1)
\end{align}$$
Now fix some $x$ and vary $y$:
$$\begin{align}
&r^\top x = s^\top y + C\\
&s^\top y = r^\top x - C\\
&\text{by (1)}\\
&s^\top y = \alpha + C - C\\
&s^\top y = \alpha &(2)
\end{align}$$

Now we can look at the differences of distinct elements $x, x' \in S$:
$$r^\top(x - x') = r^\top x - r^\top x' \underbrace{=}_{\text{by } (1)} \alpha + C - \alpha + C = 0 $$
and 
$$
s^\top (x - x') = s^\top x - s^\top x' \underbrace{=}_{\text{by } (2)} \alpha - \alpha = 0
$$


Since $S$ is infinite, there are infinite differences $d$, all of which lie in the intersection of kernels. Thus the intersection of kernels is non trivial and we can pick any $v\not = 0 \in ker(r^\top) \cap ker(s^\top)$


Next we need to pick a $w$, such that $r^\top w = s^\top w + C$. 
Observe that for any $x\not = y \ \in S$
$$\begin{align}
r^\top x = s^\top y + C, \quad r^\top x' = s^\top y + C \implies s^\top x = s^\top x'
\end{align}$$


Now pick any $x\in S$ and let $w := x + v$.
$$\begin{align}
&r^\top w = r^\top (x+ v) = r^\top x + r^\top v = r^\top x \\
=& s^\top y + C= s^\top x+C = s^\top x + s^\top v + C = s^\top (x + v) + C = s^\top w + C
\end{align}$$


Thus $r^\top w = s^\top w + C$


### AP => Ramsey Clique
Assume we are given the witnesses $v, w$ for
$$r \cdot v = 0 \land s \cdot v =0 \land r \cdot w = s \cdot w + C \land v \not = 0$$
Then the Arithmetic progression
$$a = \lbrace w + nv | n \in\mathbb Z\rbrace$$
can be interpreted as the clique witnessing
$$\exists^{ram} \textbf{x}, \textbf{y} : \varphi(x, y, c)$$
---

First observe that the AP produces distinct elements that is
$$a_i \not = a_j\quad i< j$$
because per assumption $v \not = 0$.

Next we show that every pair of elements of the sequence
 $x = w + iv$ and $y = w + jv$ for any two $i < j$, satisfies the equation.
$$\begin{align}
&rx = sy + C\\
\iff& r (w + iv) = s (w + jv) + C\\
\iff&rw + rvi = sw + svj +C\\
&\text{Since $rv = sv = 0$}\\
\iff& rw = sw +C\\
\end{align}$$
which holds exactly per our assumptions.

