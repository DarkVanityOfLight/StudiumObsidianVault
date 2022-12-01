> Jannis Lauterbach, Kilian Lichtner

## Aufgabe 1

$$\begin{align}
&{10 + n \over 1 + n} \leq 1, 01\\
\iff &10 + n \leq 1, 01 \cdot (1 + n)\\
\iff& 10 + n \leq 1,01 + 1,01 \cdot n\\
\iff& 8,99 \leq 0,01 \cdot n\\
\iff& 899 \leq n
\end{align}$$
## Aufgabe 2

### a)
Seien $n, k \in \mathbb N_0$. Wir bezeichnen mit $({n \atop k})$ die Anzahl der k-elmentigen Teilmengen einer n-elementig Menge.

Sei $A = \{1, 2, 3\}$ und $B = \{4, 5\}$. Bestimmen sie alle 4-elementigen Teilmengen von $A\cup B$, und zeigen Sie
$$\begin{align}
\left({5\atop 4}\right) = \left(3 \atop 2\right)\left( 2\atop 2\right) + \left(3 \atop 3\right)\left(2 \atop 1\right)
\end{align}$$
Alle 4 Elementigen Teilmengen:
$$\begin{align}
\{1, 2, 3, 4\}, \{1, 2, 3, 5\}, \{2, 3, 4, 5\}, \{1, 3, 4, 5\}, \{1, 2, 4, 5\}
\end{align}$$

Wir kombinieren alle 2 Elementigen Teilmengen aus der 3 Elementigen Menge(3 Verschiedene Mengen) mit allen 2 Elementigen Teilmengen aus der 2 Elementigen Menge(genau eine Menge) um Verschiedene 4 Elementigen Teilmengen zu bekommen in der jeweils 2 Elemente aus jeder Menge vorhanden sind. 
Und wir kombinieren alle 3 Elementigen Mengen aus der 3 Elementigen Menge(genau 1 Menge) mit allen 1 Elementigen Teilmengen aus der 2 Elementigen Menge(2 verschiedene Mengen) um alle Mengen mit 3 Elementen aus der einen und 1 Element aus der anderen zu bekommen.

### b)

> Anmerkung:
>  Wir bezeichnen die Menge aller n Elementigen Teilmengen einer Menge A mit $A^n$
$$\begin{align}
&\sum^{k}_{j=0} \left(n \atop j\right) \left(m \atop k-j\right) = \left(n + m \atop k \right)\\
&|A^j| + |B^{k-j}| = |(A \cup B)^k|\\
&|A^j \cup B^{k-j}| = |(A\cup B)^k|\\
&|(A\cup B)^{j+k-j}| = |(A \cup B)^k|\\
&|(A\cup B)^{k}| = |(A \cup B)^k|
\end{align}$$

## Aufgabe 3

$$\begin{align}
&|B| = 1\qquad A \cap B = \emptyset\\
&\left(n + 1 \atop k+1\right) = \left(n \atop k\right) + \left(n \atop k+1\right)\\
&|(A \cup B)^{k+1}| = |A^k| + |A^{k+1}|\\
&|(A \cup B)^{k+1}| = |(A \cup A)^{k+1}|
\end{align}$$

$$\begin{gather} \left( 0 \atop 0 \right)=1 \\ \left( 1 \atop 0 \right)=1 \qquad \left( 1 \atop 1 \right)=1 \\ \left( 2 \atop 0 \right)=1 \qquad \left( 2 \atop 1 \right)=2 \qquad \left( 2 \atop 2 \right)=1 \\ \left( 3 \atop 0 \right)=1 \qquad \left( 3 \atop 1 \right)=3 \qquad \left( 3 \atop 2 \right)=3 \qquad \left( 3 \atop 3 \right)=1 \\ \end{gather}$$


## Aufgabe 4

$$(x + 1)^0 = 1 = \sum^{0}_{k=0}\left(n \atop k\right) x^k = \left(\right)$$
$$\begin{align}
(x+1)^{n+1} = (x+1)^n \cdot (x + n)\\
= (\sum^{n}_{k=0}\left(n \atop k\right) x^k ) \cdot (x+1) = 
\end{align}$$
