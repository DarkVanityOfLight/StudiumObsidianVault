
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

---

$n\in \mathbb N\qquad a \in\mathbb Z$
Resklasse ${\over a} = \{b\in\mathbb Z| a \equiv b \mod n\}$
$$\begin{align}
a+n\in\mathbb Z :&= \{a+b | b \in n \mathbb Z\}\\
&= \{a + k \cdot n | k \in \mathbb Z\}\\
\subset \mathbb Z
\end{align}$$

$$
\mathbb Z \setminus n = \left\{\bar{0}, ..., {\over n -1}\right\}
$$

$$\begin{align}
\mathbb Z \setminus n = \{\bar 0, ..., {\over n-1}\} \text{ist Gruppe mit}\\
\bar a + \bar b := {\over a+b}
\end{align}$$

Wohldefiniert
$$\bar a_1 = \bar a_2 \qquad \bar b_1 = \bar b_2\qquad \text{z.z} \bar a_1 + \bar b_1 = \bar a_2 + \bar b_2$$

$$a_1 - a_2 = k-n \qquad b_1 - b_2 = k_i n$$
$$
\bar a_1  +b_1 = {\over a_1 + b_1} = {\over a_2 + k_i + n + b_2 + k_2 \cdot n} = {\over a_1 + b_2 + n \cdot(k_1 + k_2)} = {\over a_2 + b_2}
$$

## Beispiel
$n = 3 \qquad \mathbb Z\setminus 3 = \{\bar 0, \bar 1, \bar 2\}$

$\bar 0 = \{0, 3, -3, 6, -6 ...\}$
$\bar 1 \{1, 4, -2, ...\}$
$\bar 2 = \{2, -1, 5, 8\}$

Verknüpfung auf $\mathbb Z \setminus 3$ lässt sich durch Gruppentafel beschreiben

|+|$\bar 0$|$\bar 1$|$\bar 2$|
|-|-|-|-|
|$\bar 0$|$\bar 0$|$\bar 1$|$\bar 2$|
|$\bar 1$|$\bar 1$|$\bar 2$|$\bar 0$|
|$\bar 2$|$\bar 2$|$\bar 0$|$\bar 1$|

