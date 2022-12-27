Sind $n_1, ..., n_r \in \mathbb N$ paarweise teilerfremd un $a_1, ..., a_r \in \mathbb Z$, dann ist die simultane [Kongruenz](Kongruent.md)
$$\begin{align}
&x\equiv a_1 \mod n_1\\
&\vdots\\
&x \equiv a_r \mod n_r
\end{align}$$
lösbar. Die Lösung ist eindeutig modulo $n = n_1 \cdot ... \cdot n_r$.

Gegeben $n_1, n_2 \in \mathbb N$ teilerfremd und $a_1, a_2 \in \mathbb Z$, bestimmen wir eine Loesung der simultanen Kongruenz
$$\begin{align}
& x \equiv a_1 \mod n_1\\
& x \equiv a_2 \mod n_2
\end{align}
$$
Der erweiterte Euklidische Algorithmus liefert $u, v \in \mathbb Z$ mit
$1 = ggT(n_1, n_2) = u \cdot n_1 + v\cdot n_2$

Wegen 

$$\begin{align}
& un_1 \equiv 0 \mod n_1\\
& un_1 \equiv 1 \mod n_2\\
& vn_2 \equiv 1 \mod n_1\\
& vn_2 \equiv 0 \mod n_2
\end{align}
$$
gilt dann für
$z := a_2 \cdot u \cdot n_1 + a_1 \cdot v \cdot n_2$
dass
$$\begin{align}
& z \equiv a_1 \mod n_1\\
& z \equiv a_2 \mod n_2
\end{align}
$$
Ist $x$ eine weitere Loesung dann $n_i | (x-z)$ fuer $i = 1, 2$, und somit $n_1n_2|(x-z)$.

Insgesamt gilt 
$$
\left. x \equiv a_1 \mod n_1 \atop x \equiv a_2 \mod n_2\right\} \iff x \equiv z \mod n_1n_2
$$


## Beispiel

$$\begin{align}
&x \equiv -28 \mod 30\\
& x \equiv 5 \mod 7
\end{align}$$
Es ist $ggT(30, 7) = 7$, also ist die [Kongruenz](Kongruent.md) loesbar. Mit dem erweiterten Euklidischen Algorithmus finden wir $u$ und $v$ mit 
$u \cdot 30 + v \cdot 7 = 1$

$u = -3, v = 13$. Es gilt dann

$$\begin{align}
&(-3) \cdot 30 \equiv 0 \mod 30\\
&(-3) \cdot 30 \equiv 1 \mod 7\\
& 13 \cdot 7 \equiv 1 \mod 30\\
& 13 \cdot 7 \equiv 0 \mod 7
\end{align}$$
und somit ist
$z = (-28) \cdot (13\cdot 7) + 5 \cdot (-3 \cdot 30) = -2998$
eine Loesung (und diese ist eindeutig modulo $210$). Der Chinesiche Restsatz erlaubt uns also zwei [Kongruenzen](Kongruent.md) durch eine einzelne Kongruenz zu ersetzen:
$$
\left.x \equiv -28 \mod 30 \atop x \equiv 5\mod 7 \right\} \iff x \equiv -2998 \equiv 152 \mod 210
$$
Fuer letztere [Kongruenz](Kongruent.md) können wir die Lösungsmenge direkt angeben, sie ist 
$$152 +210 \cdot \mathbb Z = \{152 + k \cdot 210| k\in\mathbb Z\}$$
also die [Restklasse](Äquivalenzrelationen.md#Äquivalenzklasse) $\overline{152}$.
Sind die Moduli $n_i$ nicht teilerfremd, so kann man eine sehr ähnliche Lösungsformel aufstellen, allerdings kann dann die [Konvergenz](Konvergenz.md) auch unlösbar sein. Ein Kriterium gibt der folgende Satz:

> Seien $a_1, a_2 \in\mathbb Z$ und $n_1, n_2 \in\mathbb N$. Dann sind die simultanen [Kongruenzen](Kongruent.md)
> $$\begin{align}
& x \equiv a_1 \mod n_1 \\
& x \equiv a_2 \mod n_2 \\
\end{align}
 $$
 > genau dann lösbar, wenn
> $$a_1 -a_2 \equiv 0 \mod ggT(n_1, n_2)$$


---

$$\begin{align}
& x \equiv a_1 \mod n_1\\
& x \equiv a_2 \mod n_2
\end{align}$$

Modulares inverses finden:
$$\begin{align}
& n_2 \cdot x_1 \equiv 1 \mod n_1 \implies x_1 = ...\\
& n_1 \cdot x_2 \equiv 1 \mod n_2 \implies x_2 = ...
\end{align}$$

$x$ finden
$$x = a_1 \cdot n_2 \cdot x_1 + a_2 \cdot n_1 \cdot x_2$$
$x$ verkleinern
$$x \mod n_1 \cdot n_2 = ...$$
Restklasse aufschreiben

$$
R = \{x + z \cdot n_1 \cdot n_2 | \forall z \in \mathbb  Z\}
$$

#prüfungszettel 