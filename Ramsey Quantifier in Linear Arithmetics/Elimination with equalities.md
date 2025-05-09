


Assuming we already have an progression, $\lbrace a_n = x_0 +n x | n \in \mathbb N\rbrace = \lbrace a_0, a_1, \dots\rbrace  \subset \mathbb Z^d$ with the progression satisfying
$\forall i < j: r^\top a_i = s^\top a_j + C$
with $C = tz + h$
Plugging into the equation we get
$$\begin{align}
r^\top (x_0 + ix) = s^\top (x_0 + jx) + C | \text{for all $i< j$}\\
r^\top \cdot x_0 + i (r^\top\cdot x) = s^\top \cdot x_0 + j(s^\top \cdot x) + C
\end{align}$$
it is easy to see that for this to hold we require two things.
1. Both sides have a zero slope $r^\top \cdot x = s^\top \cdot x = 0$
2. We have a correct offset: that is $r^\top \cdot x_0 = s^\top \cdot x_0 + C$

From these we can derive our Presburger atoms ensuring the properties

$$\exists^{ramsey} \textbf{x}, \textbf{y}.( r^\top \textbf{x} = s^\top \textbf{y} + t^\top \textbf z + h) \iff \exists x, x. (r^\top x = 0 \land s^\top x = 0 \land r^\top x_0 = s^\top x_0 + t^\top z + h)$$

