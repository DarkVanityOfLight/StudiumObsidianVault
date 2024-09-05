
Sei $\Omega$ ein diskreter Wahrscheinlichkeitsraum mit [Wahrscheinlichkeitsfunktion](Wahrscheinlichkeitsfunktionen.md) $m: \Omega \to \mathbb R_{\ge 0}$
$$X: \Omega \to N$$
eine Zufallsvariable mit $N$ ein $\mathbb R$-[Vektorraum](Vektorräume.md). Der __Erwartungswert__ von $X$ ist dann
$$E(X) = \sum_{\omega \in\Omega} X(\omega) \cdot m(\omega)$$
falls diese Summe existiert und eindeutig ist. Anderenfalls sagen wir, dass $X$ keinen Erwartungswert hat.

Wir verlangen hier also, dass für jede Abzählung von $\Omega$ die entsprechende Reihe (bezüglich einem sinnvollen Konvergenzbegriff in $N$) konvergiert und denselben Grenzwert liefert.

Ist $\Omega$ selbst ein $\mathbb R$ Vektorraum, dann können wir insbesondere für die Zufallsvariabele die identische Abbildung $X = id$ wählen und sprechen dann von dem Erwartungswert
$$E(m) := E(id) = \sum_{\omega \in\Omega} \omega \cdot m(\omega)$$
des durch die Wahrscheinlichkeitsfunktion $m$ beschriebenen Zufallsexperiments.

Den Erwartungswert können wir auch über eine Summe im Bildraum $X$ bestimmen, denn es gilt
$$P(X = n) = \sum_{\begin{align}\omega\in\Omega \\ X(\omega) = n\end{align}} m(\omega)$$
und nach der Voraussetzung dürfen wir bei Existenz des Erwartungswerts von $X$ umsortieren, also ist
$$\begin{align}E(X) &= \sum_{\omega\in\Omega} X(\omega) \cdot m(\omega)\\ &= \sum_{n\in N} n \cdot P(X=n)\end{align}$$
indem wir alle Summanden mit $X(\omega) = n$ für festes $n$ zusammenfassen und $n$ ausklammern. Man beachte, dass $P(X = n)$ nur für abzählbar viele $n$ ungleich $0$ ist.

## Linearität

Seien $X_1 : \Omega \to N$ und $X_2: \Omega \to N$ Zufallsvariablen, für die jeweils der Erwartungswert existiert. Die Summe $X_1 + X_2$ der Zufallsvariablen ist definiert als die Zufallsvariable
$$\begin{align}
X_1 + X_2:& \Omega \to N\\
&\omega \mapsto X_1(\omega) + X_2(\omega)
\end{align}$$
Dann existiert auch der Erwartungswert von $X_1 + X_2$ und es gilt
$$E(X_1 + X_2) = E(X_1) + E(X_2)$$
Per Induktion gilt für Zufallsvariablen $X_i: \Omega\to N$, dass
$$E(X_1 + \dots + X_n) = E(X_1) + \dots + E(x_n)$$

Ist $c\in \mathbb R$ und $X: \Omega\to N$ eine Zufallsvariable, dann erhalten wir eine Zufallsvariable
$$\begin{align}
c \cdot X:& \Omega \to N\\
& \omega \mapsto c \cdot X(\omega)
\end{align}$$
Falls $E(X)$ existiert, dann auch $E(c\cdot X)$, und es gilt
$$E(c\cdot X) = c\cdot E(x)$$
## Erwartungswert des Produkts von unabhängigen Zufallsvariablen

Für die Untersuchung des Produkts von [Zufallsvariablen](Zufallsvariablen.md) $X_i: \Omega \to N$ beschränken wir uns im Folgenden auf den fall $N = \mathbb R$, da wir hier die Konvergenzfragen verstehen.

Sind $X_1 : \Omega \to \mathbb R$ und $X_2: \Omega\to\mathbb R$ unabhängige Zufallsvariablen für die die Erwartungswerte existieren. Dann gilt 
$$E(X_1 \cdot X_2) = E(X_1) \cdot E(X_2)$$
