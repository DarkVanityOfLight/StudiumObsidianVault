> Jannis Lauterbach, Gregor Stöbener, Kilian Lichtner

## Aufgabe 1 

$$
\sigma = \left(
\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7\\
2 & 1 & 5 & 6 & 4 & 3 & 7
\end{matrix}
\right)
$$

$$\begin{align}
\sigma &=(1,2)(3,5,4,6) \qquad \text{| disjunkte Zyklen}\\
&=(1,2)(2,1)(3,5)(5,4)(4,6)(6,3) \qquad \text{| Transposition}\\
\end{align}$$

Ordnung $\text{kgV}(2,4)=4$

$\text{sign}(\sigma)=(-1)^6=1$

--- 

$$
\tau = \left(
\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7\\
1 & 3 & 4 & 2 & 5 & 7 & 6
\end{matrix} \\
\right)
$$

$$\begin{align}
\tau &=(2,3,4)(6,7) \qquad \text{| disjunkte Zyklen}\\
&=(2,3)(3,4)(4,2)(6,7)(7,6) \qquad \text{| Transposition}\\
\end{align}$$

Ordnung $\text{kgV}(2,3)=6$

$\text{sign}(\sigma)=(-1)^5=-1$

---

$$
\begin{align}
\sigma \circ \tau &=\left(
\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7 \\
2 & 5 & 6 & 1 & 4 & 7 & 3
\end{matrix}
\right) \\
\end{align}
$$

$$\begin{align}
\sigma \circ \tau &=(1,2,5,4)(3,6,7) \qquad \text{| disjunkte Zyklen}\\
&=(1,2)(2,5)(5,4)(4,1)(3,6)(6,7)(7,3) \qquad \text{| Transposition}\\
\end{align}$$

Ordnung $\text{kgV}(4,3)=12$

$\text{sign}(\sigma \circ \tau)=(-1)^{7}=-1$

---

$$
\begin{align}
\tau \circ \sigma &=\left(
\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7 \\
3 & 1 & 5 & 7 & 2 & 4 & 6
\end{matrix}
\right) \\
\end{align}
$$

$$\begin{align}
\tau \circ \sigma &=(1,3,5,2)(4,7,6) \qquad \text{| disjunkte Zyklen}\\
&=(1,3)(3,5)(5,2)(2,1)(4,7)(7,6)(6,4) \qquad \text{| Transposition}\\
\end{align}$$

Ordnung $\text{kgV}(4,3)=12$
$\text{sign}(\tau \circ \sigma)=(-1)^7=-1$

## Aufgabe 2
$g^n = e$
$S_6 = \{1, 2, 3, 4, 5, 6\}$
$(1, 2, 3)$ hat die Ordnung $3$, da $(1, 2, 3)^3 = (1, 2, 3)(1, 2, 3)(1, 2,3) = (1)$
$(1, 2)(3, 4)$ hat die Ordnung $2$, da $(1, 2)(3, 4)^2 = (1, 2)(3, 4)(1, 2)(3, 4) = (1)$
$(1, 2, 3, 4, 5, 6)$ hat die Ordnung $6$, da $(1, 2, 3, 4, 5, 6)^6 = (1)$

## Aufgabe 3
### a)
$\alpha = \text{Spiegelung}$
$\beta = \text{Drehung}$

$$\begin{align}
&|G| = |Gm| \cdot |\text{Stab}(m)|\\
&|G| = |G1| \cdot |Stab(1)|\\
&|G| = |\{1, 2, 3, 4, 5, 6\}| \cdot |\{id,  2 \text{ Spiegelungen}, \text{Drehung durch}(1, 3)  \}| = 24
\end{align}$$

### b)
```GAP
gap> Order(Group((1, 2, 3, 4), (2, 5, 4, 6))))
24
```
Also 2 Erzeuger $(1, 2, 3, 4)$ und $(2, 5, 4, 6)$
### c)
```GAP
gap> Elements(Group((1, 2, 3, 4), (2, 5, 4, 6)));
[ (), (2,4)(5,6), (2,5,4,6), (2,6,4,5), (1,2)(3,4)(5,6), (1,2,3,4), (1,2,5)(3,4,6), 
  (1,2,6)(3,4,5), (1,3)(5,6), (1,3)(2,4), (1,3)(2,5)(4,6), (1,3)(2,6)(4,5), 
  (1,4,3,2), (1,4)(2,3)(5,6), (1,4,6)(2,5,3), (1,4,5)(2,6,3), (1,5,2)(3,6,4), 
  (1,5,3,6), (1,5,4)(2,3,6), (1,5)(2,4)(3,6), (1,6,2)(3,5,4), (1,6,3,5), 
  (1,6,4)(2,3,5), (1,6)(2,4)(3,5) ]
```

## Aufgabe 4

## a)
Zu zeigen:
$gH  =  Hg \forall \ g \in G$ 

Aufgrund des Index $|G : H| = 2$ gilt:
$gH \neq H \neq Hg$ 
und
$H \cup gh = G = H \cup Hg$

Wir erhalten:
$gH = (H \cup gH) \setminus H = G \setminus H = (H \cup Hg) \setminus H = Hg$
also $gH = Hg$

Somit ist H ein Normalteiler von G

## b)
$$\begin{align}
&fM = Mf \quad\forall f \in F\\
&\varphi^{-1}(fM) = \varphi^{-1}(f) \circ\varphi^{-1}(M)\\
&\varphi^{-1}(Mf) = \varphi^{-1}(M) \circ \varphi^{-1}(f)|
\end{align}$$
