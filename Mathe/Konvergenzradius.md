Der Konvergenzradius $r(P)$ von $P$ ist die kleinste [obere schranke](Schranken.md)
fuer all $x\in\mathbb R$ mit $P(x)$ konvergent, also
$$r(P) = \sup\lbrace x\in\mathbb R| P(x)\text{konvergiert}\rbrace$$
Da $P(0)$ konvergiert, ist $r(P) \ge 0$. Es ist auch $r(P) = \infty$ möglich.

> Eine Potenzreihe $P(x)$ [konvergiert](Konvergenz.md) absolut für alle $x$ mit $|x| < r(P)$ und [divergiert](Divergent) für alle $x$ mit $|x| > r(P)$.

Sei $P(x) = \sum\limits^{\infty}_{n=0} a_{n} x^{n}$ eine Potenzreihe mit $a_{n} \not = 0$ für alle $n$. Dann gilt
$$r(P) = \frac{1}{\lim_{n\to\infty} \left|\frac{a_{n+1}}{a_{n}}\right|}$$
falls der Grenzwert existiert(im Sinne von Konvergenz oder uneigentlicher Divergenz, wobei wir $\frac{1}{0} = \infty$ und $\frac{1}{\infty} = 0$ setzen).


## Entwicklungspunkt
Eine Reihe $Q(x) = \sum\limits^{\infty}_{n=0} a_{n} (x-x_{0})^n$ bezeichnen wir als [Potenzreihe](Potenzreihe.md) im Entwicklungspunkt $x_{0}$ und wir setzen $r(Q) = r(\sum\limits^{\infty}_{n=0} a_{n} x^{n})$, denn $Q(x)$ [konvergiert](Konvergenz.md) im Konvergenzradius $r(Q)$ um $x_{0}$. Damit erhalten wir eine Funktion
$$\begin{align*}
&]x_{0} - r(Q), x_{0} + r(Q) [ \to \mathbb R\\
& x \mapsto Q(x)
\end{align*}
$$
die wir mit $Q$ bezeichnen.


