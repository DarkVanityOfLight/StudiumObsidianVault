> Jannis Lauterbach, Kilian Lichtner

## Aufgabe 1

$$\begin{align}
&10 + n = 1 + n + {1 \over 100} \cdot (10 + n)\\
&n = 890
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
$$\left({n\atop k}\right) = {n! \over k! \cdot (n-k)!}$$
$$\begin{align}
\sum^{k}_{j=0} \left(n \atop j\right)\left(m \atop k-j\right) = \left(n + m \atop k\right)\\

\end{align}$$

## Aufgabe 4

$$(x+1)^n=\sum^n_{k=0}({n \atop k})x^k$$ IA: $(n=1$) $$\sum^1_{k=0}({1 \atop k})x^k y^{1-k}=y+x=(x+y)^1$$ IS: $(n + 1)$
$$\begin{align}

\end{align}$$