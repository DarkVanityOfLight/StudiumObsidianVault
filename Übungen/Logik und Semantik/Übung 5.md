
$$A_1 = \forall x.\forall y\bigl(x < y \to (\exists z.(x <z \land z < y))\bigr)$$

Die Formel is bereits "cleansed", wir bringen sie in NNF und dann in PNF:
$$\begin{align}
A_1 = &\forall x.\forall y\bigl(x < y \to (\exists z.(x <z \land z < y))\bigr)\\
A_1 = &\forall x.\forall y\bigl(\neg(x < y) \lor (\exists z.(x <z \land z < y))\bigr)\\
\iff& \forall x.\forall y. \exists z.(\neg (x < y) \lor (x < z \land z < y))
\end{align}
$$

Skolemn Normal Form:
$$\begin{align}A_1 =& \forall x.\forall y. \exists z.(\neg (x < y) \lor (x < z \land z < y))\\
\iff& \forall x.\forall y.(\neg(x < y) \lor (x < f(x, y) \land  f(x, y) < y))\end{align}$$

