
## Aufgabe 1


_a)_

Zu zeigen ist:
$$\sum^n_{j=0} \left( n \atop j \right) = 2^n$$

Sei $M$ eine Menge mit $|M| = n$.  $P(M)$ ist die Potenzmenge von $M$, das heißt die Menge aller Teilmengen von $M$. Wir wissen ausserdem $|P(M)| = 2^{|M|} = 2^n$.

Wir schreiben $\left( M \atop j \right)$ für die Menge an $j$ Elementigen Teilmengen von $M$. Die Potenzmenge enthält alle $j$ Elementigen Teilmengen, für alle $0 \le j \le n$. Die Anzahl an Elementen in der Potenzmenge ist also

$$\sum^n_{j=0} \left| \left( M \atop j\right) \right| = |P(M)| = 2^{|M|} = 2^n$$
$\square$

_b)_

Zu zeigen ist:

$$\sum^n_{j=0} \left( n \atop j\right)^2 = \left(2n \atop n\right)$$


$$\begin{align}
&\sum^n_{j=0} \left( n \atop j\right)^2 = \sum^n_{j=0} \left( n \atop j\right) \cdot \left( n \atop j\right)\\
\iff& \sum^n_{j=0} \left( n \atop j\right) \cdot \left( n \atop n-j\right) = \left( n + n \atop n\right)
\end{align}$$

## Aufgabe 2
