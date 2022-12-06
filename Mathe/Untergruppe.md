
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
