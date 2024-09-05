
Ein Wahrscheinlichkeitsbaum ist ein endlicher gerichteter [Graph](Mathe/Graph.md), der die Form eines Baumes hat und in dem alle Kanten, die aus einer Vertex herausgehen, zu den Ergebnissen desselben Zufallsexperiments korrespondieren.

Die Wurzel des Baumes geben wir die Wahrscheinlichkeit $1$. Die Wahrscheinlichkeit der weiteren Vertices berechnen sich induktiv: Korrespondiert eine Kante im Graphen zum Ergebnis $\omega$ mit Wahrscheinlichkeit $m(\omega)$ und hat der Ausgangsknoten die Wahrscheinlichkeit $p$, dann hat der Endknoten der Kante die Wahrscheinlichkeit $p \cdot m(\omega)$.

Offenbar gilt dann: Die Wahrscheinlichkeit der Blätter des Baums addieren sich zu $1$. Insbesondere beschreibt ein Wahrscheinlichkeitsbaum wieder ein Zufallsexperiment.

