Die Varianz ist ein Mass für die Streuung der Ergebnisse um den [Erwartungswert](Erwartungswert.md). Sie misst, welche Abweichung der Ergebnisse einer [Zufallsvariable](Zufallsvariablen.md) $X: \Omega \to N$ vom [Erwartungswert](Erwartungswert.md) im Mittel zu erwarten ist. Die Varianz ist also wieder ein Erwartungswert, allerdings für eine Zufallsvariable, die die Abweichung von $X$ vom Erwartungswert $E(X)$ liefert.

Es gilt
$$E(X - E(X)) = E(X) - E(E(X)) = 0$$
denn die konstante Zufallsvariable $Y = E(X)$ hat wieder den Erwartungswert
$$E(Y) = 1 \cdot E(X) = E(X)$$

Beschränken wir uns auf den Fall das $N = \mathbb R$, dann ist das Quadrat
$(X - E(X))^2$ ein sinnvolles Mass für die Abweichung, denn diese Größe ist das Quadrat des Euklidischen Abstands. Wir bemerken, das Quadrat ist leichter zu handhaben als der Betrag $|X - E(X)|$ der Abweichung, denn die Betragsfunktion ist nicht differenzierbar, was z.B. zu Problemen führt, wenn man Extremwerte bestimmen möchte.

Sei $\Omega$ ein diskreter Wahrscheinlichkeitsraum mit der [Wahrscheinlichkeitsfunktion](Wahrscheinlichkeitsfunktionen.md) $m:\Omega \to \mathbb R_{\ge 0}$ und $X: \Omega \to \mathbb R$ eine Zufallsvariable, für die der Erwartungswert existiert. Die __Varianz__ von $X$ ist
$$V(X) := E((X- E(X))^2)$$
falls dieser Erwartungswert existiert. Anderenfalls sagen wir, dass die Varianz nicht existiert.

## Standardabweichung
Die Standardabweichung von $X$ ist
$$\sigma(X) = \sqrt{V(X)}$$
Man beachte, würden wir die Wurzel vor Berechnung des Erwartungswerts ziehen, dann erhielten wir den Betrag des Abstands, denn $\sqrt{x^2} = |x|$.
Die Standardabweichung führt man ein, da in der Praxis die Werte einer [Zufallsvariablen](Zufallsvariable.md) $X$ oft mit einer Einheit kommen und die Varianz als Quadrat eine davon abweichende Einheit hat. Die Standardabweichung hat dieselbe Einheit wie die Werte von $X$.


Es gilt

$$\begin{align}
V(X) &= E((X - E(X))^2)\\
&= \sum_{\omega\in\Omega}(X(\omega) - E(X))^2 \cdot m(\omega)\\
&=\sum_{n\in N}(n-E(X))^2 \cdot P(X = n)\\
\end{align}$$
wobei nach Voraussetzung die erste Summe absolut konvergent ist, ebenso die zweite Summe.

Konvergiert die Summe
$$E(X) = \sum_{\omega \in\Omega} X(\omega) \cdot m(\omega)$$
zur Berechnung des Erwartungswerts absolut, dann muss
$$\sum_{\omega\in\Omega} (X(\omega) - E(X))^2 \cdot m(\omega)$$
nicht notwendig konvergieren.

Die Varianz von $X$ lässt sich aus den Erwartungswerten von $X^2$ und $X$ berechnen als
$$V(X) = E(X^2) - E(X)^2$$
Ist $X: \Omega \to \mathbb R$ eine Zufallsvariable fuer die Varianzexistiert und $c\in\mathbb R$, dann gilt 
$$V(c \cdot X) = c^2 \cdot V(X)$$
und
$V(X + c) = V(X)$

## Momente
Die Erwartungswerte $E(X^k)$ für $k \in\mathbb N$ bezeichnet man auch als die Momente von $X$. Die Existenz von $E(X^{k+1})$ impliziert die Existenz von $E(X^k). Existiert $E(X^2)$ dann also auch $V(X)$ und $E(X)$.


## Varianz von Summe und Produkt unabhängiger Zufallsvariablen

Sind $X_1: \Omega \to \mathbb R$ und $X_2: \Omega \to\mathbb R$ unabhängige Zufallsvariablen für die jeweils die Varianz existiert, dann gilt
$$V(X_1 + X_2) = V(X_1) + V(X_2)$$
und
$$V(X_1 \cdot X_2) = V(X_1) \cdot E(X_2) + E(X_1) \cdot V(X_2) + V(X_1) \cdot V(X_2)$$
