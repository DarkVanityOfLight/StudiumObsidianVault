
$$T(n) \le \left\lbrace \begin{align*}
&c &\text{ wenn } n <  4\\
&3T\left(\frac{n}{4}\right)+ d \cdot n^{2} &\text{ wenn } n > 4
\end{align*}\right.$$

## Ansatz
Wiederholtes Einsetzen der Rekursionsungleichung

$$
\begin{align*}
T(n) &\le 3 \cdot T\left(\frac{n}{4}\right) + d \cdot n^2\\
&\le  3 \cdot \left(3 \cdot T\left(\frac{n}{16}\right) + d \cdot \left(\frac{n}{4}\right)^{2} \right) + d \cdot n^2\\
&\le  3 \cdot \left(3 \cdot \left(3 \cdot T\left(\frac{n}{64}\right)+ d \left(\frac{n}{16}\right)^{2}\right)+ d \cdot \left(\frac{n}{4}\right)^{2} \right)+ d \cdot n^{2}\\
&\le \quad...
\end{align*}
$$
Schreibweise als Rekursionsbaum:
$$\begin{align*}
T(n) &\le \underbrace{3 \cdot T\left(\frac{n}{4}\right)}_{\text{Rekursiver Teil}}+ \underbrace{d \cdot n^{2}}_{\text{Nichtrekursiver Teil}}
\end{align*}$$

Für den Rekursiven Teil:
$$\frac{n}{4^{i}} = 1 \iff i = \log_{4} n$$

Für den nicht Rekursiven Teil:

$$3^{\log_{n} n } T(1) = 3^{\log_{2} n } \cdot C$$

Damit gilt
$$\begin{align*}
T(n) &\le \left(\sum\limits^{log_{n}(n) - 1}_{i = 0} 3^{i}\cdot d \cdot \frac{n}{4^{i}} + 3^{\log_{4} n }\right) \cdot C\\
&= d \cdot n^{2} \cdot \sum\limits^{\log_{4}(n) - 1}_{i=0} \left(\underbrace{\frac{3}{16}}_{<1}\right)^{i} + n^{\log_{4}3} \cdot C\\
&\le \sum\limits^{\infty}_{i=0} \left(\frac{3}{16}\right)^{i} \in O(1)\\
&= O(n^{2}\qquad + n^{\log_{4}3})\\
&= O(n^2)
\end{align*}$$
