
$$A_1 = \forall x.\forall y\bigl(x < y \to (\exists z.(x <z \land z < y))\bigr)$$

Die Formel is bereits "cleansed", wir bringen sie in NNF:
$$\begin{align}
A_1 = &\forall x.\forall y\bigl(x < y \to (\exists z.(x <z \land z < y))\bigr)\\
A_1 = &\forall x.\forall y\bigl(\neg(x < y) \lor (\exists z.(x <z \land z < y))\bigr)\\
\end{align}
$$
