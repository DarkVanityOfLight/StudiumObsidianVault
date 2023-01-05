> Jannis Lauterbach, Kilian Lichtner


## Aufgabe 1

Wenn wir die beiden Cauchyfolgen $(a_n)$ und $(b_n)$ addieren erhalten wir eine neue Folge $(c_n)$ wobei $c_n = a_n + b_n$

$(c_n)$ ist nun auch eine Cauchyfolge da es für jedes $\epsilon >0$ eine natürliche Zahl $N$ gibt, sodass $|c_n - c_m| < \epsilon \forall n,m > N$. Wir setzen $N = \max(N_a, N_b)$. Dann gilt für all $n, m > N$

$$|c_n - c_m| = |(a_n + b_n) - (a_m + b_m)| = |a_n - a_m| + |b_n - b_m| < {\varepsilon\over 2} + {\varepsilon \over 2} = \varepsilon$$
Daher ist $(c_n)$ eine Cauchy Folge.

## Aufgabe 2

### a)
Weil $(a_n)$ nicht gegen $0$ konvergiert gibt es ein $\varepsilon > 0$  sodass  für alle $N \in \mathbb N$ mindestens ein $n \geq N$ existiert für das gilt $|a_n| \geq \varepsilon$.
Nehmen wir eines dieser $\varepsilon$ und betrachten $\frac{\varepsilon}{2} > 0$

Da $(a_n)$ eine Cauchyfolge ist existiert ein $M \in \mathbb N$ mit
$\forall m, n \geq M: |a_n - a_m| < \frac{\varepsilon}{2}$
Außerdem existiert ein $x \in M$ mit $|a_x| > \varepsilon$
Deshalb $\forall m \geq M: |x - a_m| < \frac{\varepsilon}{2}$

Damit gelten kann $\forall m \geq M: |x - a_m| < \frac{\varepsilon}{2}$ muss auch gelten $\forall m \geq M: |a_m| > \frac{\varepsilon}{2}$.

$C := \min(|a_1|, ..., |a_n||\forall n < M)$
Dann ist $|a_n| \geq C$ für alle $k < M$ und $|a_n| \geq \frac{\varepsilon}{2}\forall n\geq M$

### b)
$\varepsilon > 0$. $\exists N$  mit $\forall n, m > N$ gilt  $|a_n - a_m| < \varepsilon$

Da wir schon ein $C$ mit $C < 0 < |a_n| \forall n$ bestimmt haben gilt

$$\begin{align}
\left|\frac{1}{a_n} - \frac{1}{a_m} \right| = \frac{1}{|a_m| \cdot |a_n|} \cdot |a_n -a_m| < \frac{\varepsilon}{C^2}
\end{align}$$

### Aufgabe 3

## a)


Die Rekursive Folge:
$$\begin{align}
a_{n+1} = \sqrt{1 + a_n}\\
\end{align}$$

Hat den Grenzwert $g$(negativen Grenzwert weglassen da, dieser keinen Sinn ergibt)
$$\begin{align*}
&g = \sqrt{1+ g}\\
\iff & \sqrt{g +1} = g\\
\iff& g + 1 = g^2\\
\iff& -g^2 + g+ 1 = 0\\
\iff& g^2 -g -1 = 0\\
\iff& g^2 -g = 1\\
\iff& g^2 - g + \frac{1}{4} = \frac{5}{4}\\
\iff& \left(g - \frac{1}{2}\right)^2 = \frac{5}{4}\\
\iff& g - \frac{1}{2} = \frac{\sqrt{5}}{2}\\
\iff& g= \frac{\sqrt{5}}{2} + \frac{1}{2} \\
\iff& g = \frac{1}{2}(\sqrt{5} + \frac{1}{2})
\end{align*}$$
Also $g \approx 1.618033$

### Aufgabe 4

Die Rekursive Folge 
$$
c_{n+1} = \frac{1}{2}(c_n + \frac{d}{c_n})
$$
Hat die beiden Grenzwerte $g_1, g_2$:

$$\begin{align*}
&g = \frac{1}{2} (g + \frac{d}{g})\\
\iff&g = \frac{1}{2} g + \frac{d}{2g}\\
\iff&\frac{1}{2}g = \frac{d}{2g}\\
\iff& \frac{1}{2}\cdot g^2 = d\\
\iff& g^2 = d\\
\iff& g_1 = \sqrt{d} \land g_2 = -\sqrt{d}
\end{align*}$$
Wobei nur der Grenzwert $g_1$ Sinn ergibt.

