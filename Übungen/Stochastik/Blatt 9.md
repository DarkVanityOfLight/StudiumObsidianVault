
> Kris Grohe, Kilian Lichtner
## Aufgabe 1

_a)_

$P(X_1 = n) = P(X_2 = n) = \frac{1}{6}\quad n\in\lbrace 1, 2, 3, 4, 5, 6\rbrace$

_b)_
$X_1 + X_2$
$\Omega \to \lbrace 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12\rbrace$

Die Wahrscheinlichkeit einer Kombination $(a, b)$ ist genau $\frac{1}{6} \cdot \frac{1}{6} = \frac{1}{16}$, dann bleibt zu zählen wie viele Möglichkeiten es für jede Summe gibt
$$\begin{align}
&P(X_1 + X_2 = 2) = P(X_1 + x_2 = 12) = 1 \cdot \frac{1}{36}\\
&P(X_1 + X_2 = 3) = P(X_1 + x_2 = 11) = 2 \cdot \frac{1}{36}\\
&P(X_1 + X_2 = 4) = P(X_1 + x_2 = 10) = 3 \cdot \frac{1}{36}\\
&P(X_1 + X_2 = 5) = P(X_1 + x_2 = 9) = 4 \cdot \frac{1}{36}\\
&P(X_1 + X_2 = 6) = P(X_1 + x_2 = 8) = 5 \cdot \frac{1}{36}\\
&P(X_1 + X_2 = 7) = 6 \cdot \frac{1}{36}\\
\end{align}$$
$X_1 - X_2$
$\Omega \to \lbrace -5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5\rbrace$
$$\begin{align}
&P(X_1 + X_2 = -5) = P(X_1 + x_2 = 5) = 1 \cdot \frac{1}{36}\\
&P(X_1 + X_2 = -4) = P(X_1 + x_2 = 5) = 2 \cdot \frac{1}{36}\\
&P(X_1 + X_2 = -3) = P(X_1 + x_2 = 3) = 3 \cdot \frac{1}{36}\\
&P(X_1 + X_2 = -2) = P(X_1 + x_2 = 2) = 4 \cdot \frac{1}{36}\\
&P(X_1 + X_2 = -1) = P(X_1 + x_2 = 1) = 5 \cdot \frac{1}{36}\\
&P(X_1 + X_2 = 0) = 6 \cdot \frac{1}{36}\\
\end{align}$$

## Aufgabe 2
Es gibt insgesamt $2^3 = 8$ Verschiedene Tupel:

| 1   | 2   | 3   |
| --- | --- | --- |
| 0   | 0   | 0   |
| 0   | 0   | 1   |
| 0   | 1   | 0   |
| 0   | 1   | 1   |
| 1   | 0   | 0   |
| 1   | 0   | 1   |
| 1   | 1   | 0   |
| 1   | 1   | 1   |

- $P(X_1) = \frac{3}{8}$
- $P(X_2) = \frac{4}{8}$
- $P(X_3) = 1 \cdot \frac{3}{8} + 2 \cdot \frac{3}{8} + 3 \cdot \frac{1}{8} = \frac{3}{2}$

$X_1 \cdot X_3 = \frac{3}{8} \cdot \frac{3}{2} = \frac{9}{16}$
$X_2 \cdot X_3 = \frac{4}{8} \cdot \frac{3}{2} = \frac{3}{4}$


## Aufgabe 3
Sei $\Omega \to \lbrace 1, 2, 3, 4, 5, 6\rbrace$
Sei $X$ eine Zufallsvariable 
$$\begin{align}
X: &\Omega \to \mathbb N\\
&n \mapsto 2(n+1)
\end{align}$$

Dann ist der Erwartungswert gegeben durch
$$\begin{align}
&E(X) = \sum^{}_{\omega \in \Omega} m(\omega) \cdot X(\omega)\\
&E(X) =  \sum^6_{i=1} \frac{1}{6} \cdot 2(i+1) = 9
\end{align}$$

Die Varianz ist dann
$$\begin{align}
V(X) &= \sum_{\omega\in\Omega} (X(\omega) - E(X))^2 \cdot m(\omega)\\
&=  \sum_{i=1}^6 (2(i+1) - 9)^2 \cdot \frac{1}{6} = \frac{35}{3}
\end{align}$$


## Aufgabe 4

_a)_
Wir zeigen per Induktion das
$$
\sum^n_{i=1} i^2 = \frac{n\cdot  (n+1) \cdot (2n + 1)}{6}
$$

__Indkutionsanfang__
Sei $n = 0$, dann

$$\sum^0_{i=1} i^2 = 0$$
und 
$$\frac{0\cdot  (0+1) \cdot (2\cdot0 + 1)}{6} = \frac{0}{6} = 0$$

__Induktionsvoraussetzung__
Für ein beliebiges aber festes $n$ gelte 
$$
\sum^n_{i=1} i^2 = \frac{n\cdot  (n+1) \cdot (2n + 1)}{6}
$$

__Induktionsschritt__ $n\mapsto n+1$

Zu zeigen ist also

$$\begin{align}
\sum^{n+1}_{i=1} i^2 &= \frac{(n+1)\cdot  (n+2) \cdot (2(n+1) + 1)}{6}\\
&= \frac{(n+1)\cdot  (n+2) \cdot (2n+ 3)}{6}\\
&= \frac{2n^3 + 9n^2 + 13n + 6}{6}
\end{align}$$
---

$$\begin{align}
&\sum^{n+1}_{i=1} i^2\\
\iff&\sum^{n}_{i=1} i^2 + (n+1)^2\\
\iff& (n+1)^2 + \sum^n_{i=1} i^2\\
IV\atop\iff& (n+1)^2 + \frac{n\cdot  (n+1) \cdot (2n + 1)}{6}\\
\iff& \frac{6 \cdot (n+1)^2}{6} + \frac{n\cdot  (n+1) \cdot (2n + 1)}{6}\\
\iff&\frac{6 \cdot (n+1)^2 + n\cdot  (n+1) \cdot (2n + 1)}{6}\\
\iff&\frac{6n^2 + 12n+ 6 + n\cdot  (n+1) \cdot (2n + 1)}{6}\\
\iff&\frac{6n^2 + 12n+ 6 + 2n^3 + 3n^2 + n}{6}\\
\iff&\frac{9n^2 + 13n+ 2n^3 + 6}{6}\\
\iff&\frac{2n^3 + 9n^2 + 13n + 6}{6}
\end{align}$$
$\blacksquare$

_b)_
Sei $\Omega \to \lbrace 1, \dots, n\rbrace$
$$\begin{align}
X:& \Omega \to \mathbb N\\
& n\mapsto n
\end{align}$$


__i)__ Der Erwartungswert ist definiert durch
$$\begin{align}
E(X) &= \sum_{\omega\in\Omega} m(\omega) \cdot X(\omega)\\
E(X) &= \sum_{i=1}^n \frac{1}{n} \cdot i\\
\iff& \frac{1}{n} \cdot \sum_{i=1}^n i\\
\iff& \frac{1}{n} \cdot \frac{n\cdot (n+1)}{2}\\
\iff& \frac{n\cdot(n+1)}{2n}\\
\iff& \frac{n+1}{2}\\
\blacksquare
\end{align}$$


__ii)__ Die Varianz ist definiert durch

$$\begin{align}
V(X) &= \sum_{\omega\in\Omega} (X(\omega) - E(X))^2 \cdot m(\omega)\\
V(X) &= \sum_{i=1}^n (X(i) - E(X))^2 \cdot \frac{1}{n}\\
\text{Per i) gilt}\atop\iff& \sum_{i=1}^n \left(X(i) - \frac{n+1}{2}\right)^2 \cdot \frac{1}{n}\\
\iff& \sum_{i=1}^n \left(i - \frac{n+1}{2}\right)^2 \cdot \frac{1}{n}\\
\iff& \frac{1}{n} \left(\sum_{i=1}^n \left(i - \frac{n+1}{2}\right)^2\right)\\

\iff& \frac{1}{n} \left(\sum^n_{i=1} i^2 - \sum^n_{i=1} 2i \frac{n+1}{2} + \sum^n_{i=1} \left(\frac{n+1}{2}\right)^2\right)\\

\text{Per a)}\atop \iff& \frac{1}{n} \left(\frac{n(n+1)(2n+1)}{6} - \frac{n(n+1)^2}{2} + n\cdot \left(\frac{n+1}{2}\right)^2\right)\\

\iff& \frac{1}{n} \left(\frac{n(n+1)(2n+1)}{6} - \frac{2n(n+1)^2}{4} + \frac{n(n+1)^2}{4}\right)\\

\iff& \frac{1}{n} \left(\frac{n(n+1)(2n+1)}{6} - \frac{n(n+1)^2}{2} + \frac{n(n+1)^2}{4}\right)\\

\iff& \frac{1}{n} \left(\frac{n(n+1)(2n+1)}{6} - \frac{3n(n+1)^2}{6} + \frac{n(n+1)^2}{4}\right)\\

\iff& \frac{1}{n} \left(\frac{n(n+1)(2n+1)- 3n(n+1)^2}{6} + \frac{n(n+1)^2}{4}\right)\\

\iff& \frac{1}{n} \left(\frac{2n(n+1)(2n+1)- 6n(n+1)^2}{12} + \frac{3n(n+1)^2}{12}\right)\\

\iff& \frac{1}{n} \left(\frac{2n(n+1)(2n+1)- 3n(n+1)^2}{12} \right)\\
\iff& \left(\frac{2(n+1)(2n+1)- 3(n+1)^2}{12} \right)\\
\iff& \frac{(n-1)(n+1)}{12}\\
\blacksquare
\end{align}$$


