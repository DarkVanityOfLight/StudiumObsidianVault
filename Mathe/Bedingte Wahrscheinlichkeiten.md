
Sei $\Omega$ ein diskreter Wahrscheinlichkeitsraum mit [Wahrscheinlichkeitsfunktionen](Wahrscheinlichkeitsfunktion.md) $m: \Omega \to \mathbb R_{\ge 0 }$. In vielen Situationen will man die Wahrscheinlichkeit wissen, mit der ein Ergebnis $\omega$ auftritt unter der Voraussetzung, dass ein festgelegtes Ereignis $E$ eintritt. Klar ist, dass für $\omega\not\in E$, das Ergebnis nicht eintreten, kann die Wahrscheinlichkeit ist also $0$.
Für alle $\omega\in E$ sollte die Wahrscheinlichkeit $m'(\omega)$, dass $\omega$ eintritt unter der Voraussetzung, dass $E$ eintritt proportional zu $m(\omega)$ sein, das heißt es gibt ein $c\in\mathbb R$ mit 
$$m'(\omega) = c \cdot m(\omega) | \forall \omega \in E$$

Da anderseits die Wahrscheinlichkeit des [Ereignisses](Ereignisse.md) $E$ unter Voraussetzung, dass $E$ eintritt gleich $1$ sein muss, gilt
$$1 = \sum_{\omega\in\Omega} m'(\omega) = \sum_{\omega\in E} m'(\omega) = c \cdot \sum_{\omega \in E} m(\omega)$$
also
$$c = \frac{1}{\sum_{\omega\in E} m(\omega)} = \frac{1}{P(E)}$$

Für ein Ereignis $E\subset\Omega$ mit $P(E) > 0$ und ein Ergebnis $\omega \in \Omega$ schreiben wir für die __bedingte Wahrscheinlichkeit__ von $\omega$ unter der Voraussetzung dass $E$ eintritt,
$$m(\omega | E) = \begin{cases}\frac{m(\omega)}{P(E)} \text{ falls } \omega\in E\\
0\qquad\text{sonst}\end{cases}$$

Es gilt dann
$$\sum_{\omega\in\Omega}m(\omega | E) = \sum_{w\in E} m(\omega | E) = \frac{P(E)}{P(E)} = 1$$

durch
$$\begin{align}
m(-| E):& \Omega\to \mathbb R_{\ge 0}\\
&\omega\mapsto m(\omega | E)
\end{align}$$
ist als wieder eine Wahrscheinlichkeitsfunktion auf $\Omega$ gegeben.

Für ein Ereignis $F\subset \Omega$ schreiben wir für die bedingte Wahrscheinlichkeit von $F$ unter der Voraussetzung, dass $E$ eintritt,
$$P(F|E) = \sum_{\omega\in F} m(\omega | E)$$
Es gilt dann
$$P(F|E) = \sum_{\omega F\cap E} \frac{m(\omega)}{P(E)} = \frac{P(F\cap E)}{P(E)}$$
insbesondere für $F\subset E$ ist
$$P(F | E) = \frac{P(F)}{P(E)}$$
