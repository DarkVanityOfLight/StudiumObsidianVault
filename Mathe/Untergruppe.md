
Sei $(G, \circ)$ eine [Gruppe](Gruppe.md)
$H\subset G$ heißt Untergruppe wenn die folgenden beiden äquivalenten Bedingungnen erfüllt sind

1. $(H, \circ)$ ist eine Gruppe
2. $H \not = \emptyset \qquad a,b \in H \implies a\circ b^{-1} \in H$

## Beweis 

$$\begin{align}
(1) \implies (2)
\end{align}$$

$$\begin{align}
(2)\implies (1): H \not = \emptyset \implies \exists a\in H \implies e= a\circ a^{-1} \in H
\end{align}$$
Also $b\in H \implies b^{-1} = e \circ b^{-1} \in H$
$a\circ b = a \circ (b^{-1})^{-1} \in H$

---

$n \mathbb Z \subset \mathbb Z$ Ist eine Untergruppe
$$\begin{align}
4 \in 2 \mathbb Z \ni 0\\
-4
\end{align}$$

$$\begin{align}
a, b \in n \mathbb Z\\
a = k \cdot n\\
b = k' \cdot n\\
a+b = kn +k'n = (k + k') n
\end{align}$$

$$\begin{align}
H\in \mathbb Z\quad\text{Untergruppe}\quad H =\{0\} = 0\mathbb Z\\
H \not = \{0\} \text{existiert kleinstes Element von H}
\end{align}$$

Zeige $H = n \mathbb Z$


Sei $m\in H$
[Division mit Rest](Division%20mit%20Rest.md) $m= q\cdot n +r\qquad 0 \leq r < n$
$\implies r \in H$

$\implies m = q \cdot n \in n\mathbb Z$
