Oft will man bei einem Zufallsexperiment nur eine aus den Ergebnissen abgeleitete Größe untersuchen. Dazu betrachtet man eine Abbildung, die einem Ergebnis die abgeleitete Größe zuordnet, und hier die Wahrscheinlichkeit mit der diese Größe einen bestimmten Wert annimmt.

Auf einem diskreten [Wahrscheinlichkeitsraum](Wahrscheinlichkeitsfunktionen.md) mit Ergebnisraum $\Omega$ und Wahrscheinlichkeitsfunktion
$$m: \Omega \to \mathbb R_{\ge 0}$$
ist eine Zufallsvariable $X$ eine Abbildung
$$X: \Omega \to N$$
in eine [Menge](Mengen.md) $N$, die als Bildraum von $X$ bezeichnet wird. Die Verteilung der Zufallsvariable $X$ im Bildraum $N$ ist gegeben durch die Funktion
$$\begin{align}
m_X:& N\to \mathbb R_{\ge 0}\\
& n\mapsto P(X^{-1}(\lbrace n\rbrace))
\end{align}$$
Wir bilden also das Urbild von $n$ unter der [Abbildung](Abbildungen.md) $X$ und von diesem Ereignis die Wahrscheinlichkeit.

---

Man verwendet auch die Notation 
$$P(X = n) := m_X (n) = P(X^{-1}(\lbrace n\rbrace))$$

Nach der gilt
$$P(X = n) = \sum_{\begin{align}\omega \in\Omega\\ X(\omega) = n \end{align}} m(\omega)$$
Es gilt
$$\sum_{n\in N} P(X = n) = 1$$

## Unabhängigkeit

Für Zufallsvariablen $X_1 : \Omega \to N_1$ und $X_2 :\Omega \to N_2$ bilden wir die Zufallsvariable
$$(X_1, X_2): \Omega \to N_1 \times N_2$$
für die Verteilung dieser Zufallsvariable schreiben wir auch
$$P(X_1 = n_1, X_2 = n_2) := P((X_1, X_2) = (n_1, n_2))$$

Die Zufallsvariablen $X_1: \Omega \to N_1$ und $X_2: \Omega \to N_2$ heißen unabhängig, wenn
$$P(X_1 = n_1, X_2 = n_2) = P(X_1 = n_1) \cdot P(X_2 = n_2)$$
für alle $(n_1, n_2) \in N_1 \times N_2$

---

Sei $\Omega$ ein diskreter Wahrscheinlichkeitsraum mit der [Wahrscheinlichkeitsfunktion](Wahrscheinlichkeitsfunktion.md) $m: \Omega \to \mathbb R_{\ge 0}$, sei $X: \Omega \to\mathbb R$ eine Zufallsvariable und $c\in \mathbb R$. Wir schreiben
$$P(x \ge c) = \sum_{\begin{align}
\omega \in \Omega\\ X(\omega) \ge c
\end{align}}m(\omega)$$
für die Wahrscheinlichkeit, dass $X$ Werte $\ge c$ annimmt, also für die Wahrscheinlichkeit des Ereignisses
$$\lbrace \omega\in\Omega |
X(\omega) \ge c\rbrace$$


## Stochastisch äquivalent 
Zwei Zufallsvariablen $X_1, X_2: \Omega \to \mathbb R$ heissen stochastisch aequivalent, geschrieben
$$X_1 \sim X_2$$
wenn
$$P(X_1 - X_2 = 0) = 0$$
Dies bedeutet also, dass das Ereignis aller $\omega\in\Omega$ mit $X_1(\omega) \not = X_2(\omega)$ die Wahrscheinlichkeit $0$ hat.

## Unabhängig und identisch verteilt

Wir sagen, dass Zufallsvariablen $X_1, \dots, X_n: \Omega \to \mathbb R$ auf dem diskreten Wahrscheinlichkeitsraum $\Omega$ __unabhängig und identisch verteilt__ sind, falls für alle $i$ die Verteilungsfunktionen $a\mapsto P(X_i = a)$ übereinstimmen und 
$$P(X_1 = a_1, \dots, X_n = a_n) = P(X_1 = a_1) \cdot ... \cdot P(X_n = a_n)$$
für alle $a_1, \cdot, a_n$.
