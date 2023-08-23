
Wir berechnen die Uebertraege aller Stellen schneller.
Als Definition von $c_{i+1}$ haben wir bisher:
$$c_{i+1} = \underbrace{x_i \land y_i}_{\text{Generate}} \lor \underbrace{(x_i \lor y_i)}_{\text{Propagate}} \land c_i$$

Das Carry besteht also aus zwei Teilen Generated und Propagated.

Wir definieren Generate als $g_i := x_i \land y_i$ und Propagate als $p_i := x_i \lor y_i$, dann erhalten wir:
$c_{i+1} = g_i \lor p_i \land c_i$

Wir müssen trotzdem $c_0 \leadsto c_1 \leadsto \dots \leadsto c_{n-1}$ unterbrechen.

## Carry Berechnung als [Parallel Präfix Problem](Parallel%20Präfix%20Problem.md)

Wir definieren einen Binäroperator $\odot: \mathbb B^2 \times \mathbb B^2 \to \mathbb B^2$ folgendermaßen:
$$(g_2, p_2) \odot (g_1, p_1) := (g_2 \lor p_2 \land g_1, p_2 \land p_1)$$

Die Operation ist Assoziativ und alle Carry Stellen können als Parallele Präfix Summe mit $\odot$ folgendermaßen berechnet werden:
$$(c_{i+1}, \bigwedge^i_{j=0} p_j) \iff (g_i, p_i) \odot \dots \odot (g_0, p_0) \odot (c_0, 1)$$
Nun können wir einen der Parallel Präfix Algorithmen verwenden um alle Carry Bits zu berechnen.



