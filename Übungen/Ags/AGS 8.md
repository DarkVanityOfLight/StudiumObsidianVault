
> Jannis Lauterbach, Gregor Stöbener, Kilian Lichtner

## Aufgabe 1

### a)
Berechnen wir das Signum für

$$sign\left(\begin{matrix}
1 & 2& 3& 4& 5& 6 & 7 & 8 & 9 &10 &11 & 12& 13 & 14 & 15\\
2 & 1 & 3& 4& 5& 6 &7 &8 & 9 & 10& 11& 12& 13 & 14 & 15\end{matrix}\right) = -1$$
und 
$$sign\left(\begin{matrix}
1 & 2& 3& 4& 5& 6 & 7 & 8 & 9 &10 &11 & 12& 13 & 14 & 15\\
1 & 2& 3& 4& 5& 6 & 7 & 8 & 9 &10 &11 & 12& 13 & 14 & 15
\end{matrix}\right) = 1$$
da wir genau eine Transposition haben $\left(\begin{matrix} 1 &2\\2&1 \end{matrix}\right)$ also $(-1)^1$ und $(-1)^0$.
Da die Signatur nun allerdings ein Gruppenhomomorphismus ist müssten die beiden Signum werte gleich sein. Da dies nicht der Fall ist ist es nicht möglich die Beiden Konfigurationen durch einfache Transposition ineinander zu überführen.


### b)
Die Signatur einer permutation ist definiert als $(-1)^k$, wobei $k$ die Anzahl an Transpositionen ist die wir brauchen um die Permutation als Produkt von Transpositionen darzustellen.
Da $\tau$ eine Transposition ist ist $k = 1$ und $sign(\tau) = (-1)^1 = -1$.

## Aufgabe 2

### a)
$$\begin{align}
&ord(x\circ y) = kgV(ord(x), ord(y))\\
\end{align}$$


### b)

$$
\begin{align}
\sigma &= \left(
\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7\\
2 & 1 & 5 & 6 & 4 & 3 & 7
\end{matrix}
\right) \\
&=(1,2)(3,5,4,6)(7)
\end{align}
$$

$${1,...,7}={1,2}\bigcup^{\cdot}{3,4,5,6}\bigcup^\cdot{7}$$

Ordnung $\text{kgV}(2,4,1)=4$

---

$$
\begin{align}
\tau &= \left(
\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7\\
1 & 3 & 4 & 2 & 5 & 7 & 6
\end{matrix}
\right) \\
&=(1)(2,3,4)(5)(6,7)
\end{align}
$$

Ordnung $\text{kgV}(1,3,1,2)=6$

---

$$
\begin{align}
\sigma \circ \tau &=\left(
\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7 \\
2 & 5 & 6 & 1 & 4 & 7 & 3
\end{matrix}
\right) \\
&=(1,2,5,4,)(3,6,7)
\end{align}
$$

Ordnung $\text{kgV}(4,3)=12$

---

$$
\begin{align}
\tau \circ \sigma &=\left(
\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7 \\
3 & 1 & 5 & 7 & 2 & 4 & 6
\end{matrix}
\right) \\
&=(1,3,5,2)(4,7,6)
\end{align}
$$

Ordnung $\text{kgV}(4,3)=12$

## Aufgabe 3

### a)
$\alpha = \text{Spiegelung}$
$\beta = \text{Drehung}$

$$
G = S_5 = \langle \alpha,\beta \rangle = \{id, \alpha, \beta, \beta^2, \beta^3, \beta^4, \alpha\beta, \alpha\beta^2, \alpha\beta^3, \alpha\beta^4\}
$$

$$\begin{align}
&|G| = |G m| \cdot |\text{Stab}(m)|\\
&|G| = |G 1| \cdot |\text{Stab}(1)|\\
&|G| = |\{1, 2, 3, 4, 5\}| \cdot |\{id, \alpha\}|\\
&|G| = 5 \cdot 2 = 10
\end{align}$$

### b)

| Element    | Permutation                |
|------------|----------------------------|
| Rotation   | $\texttt{(1 2 3 4 5)}$     |
| Rotation   | $\texttt{(2 3 4 5 1)}$     |
| Rotation   | $\texttt{(3 4 5 1 2)}$     |
| Rotation   | $\texttt{(4 5 1 2 3)}$     |
| Rotation   | $\texttt{(5 1 2 3 4)}$     |
| Spiegelung | $\texttt{(1 5)(2 4)(3 3)}$ |
| Spiegelung | $\texttt{(1 4)(2 5)(3 3)}$ |
| Spiegelung | $\texttt{(1 3)(2 2)(3 5)}$ |
| Spiegelung | $\texttt{(1 2)(2 3)(3 4)}$ |
| Spiegelung | $\texttt{(1 1)(2 2)(3 4)}$ |

### c)

Da es sich hierbei um eine regelmäßiges 5-Eck handelt wissen wir, dass es $2^5=32$ Untergruppen geben muss.

1. ${}$
2. $\{1\}$
3. $\{2\}$
4. $\{3\}$
5. $\{4\}$
6. $\{5\}$
7. $\{1,2\}$
8. $\{1,3\}$
9. $\{1,4\}$
10. $\{1,5\}$
11. $\{2,3\}$
12. $\{2,4\}$
13. $\{2,5\}$
14. $\{3,4\}$
15. $\{3,5\}$
16. $\{4,5\}$
17. $\{1,2,3\}$
18. $\{1,2,4\}$
19. $\{1,2,5\}$
20. $\{1,3,4\}$
21. $\{1,3,5\}$
22. $\{1,4,5\}$
23. $\{2,3,4\}$
24. $\{2,3,5\}$
25. $\{2,4,5\}$
26. $\{3,4,5\}$
27. $\{1,2,3,4\}$
28. $\{1,2,3,5\}$
29. $\{1,3,4,5\}$
30. $\{1,3,4,5\}$
31. $\{2,3,4,5\}$
32. $\{1,2,3,4,5\}$

## Aufgabe 4

$$\begin{align}
&|G| = |Gm| \cdot |\text{Stab}(m)|\\
&|G| = |G1| \cdot |Stab(1)|\\
&|G| = |\{1, 2, 3, 4, 5, 6\}| \cdot |\{id,  \text{Spiegelung}| = 12
\end{align}$$
