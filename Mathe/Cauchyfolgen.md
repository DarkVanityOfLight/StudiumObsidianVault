Sei $K$ ein [Angeordneter Koerper](Angeordneter%20Koerper.md). Eine [Folge](Folgen.md) heißt Cauchyfolge, wenn es zu jedem $\epsilon > 0$ ein $N \in \mathbb N$ gibt mit 
$$
|a_n - a_m| < \epsilon\ \text{fuer alle } n,m \geq N
$$
Der Abstand zwischen den Folgegliedern wird also beliebig klein.

---

Sei $K$ ein angeordneter [Körper](Körper.md). Jede [konvergente](Konvergenz.md) [Folge](Folgen.md) ist eine Cauchyfolge.

## Beweis
Ist $(a_n)$ konvergent gegen $a\in K$, dann gibt es zu jede $\epsilon < 0$ ein $N$ mit 
 $$
 |a_n - a| < {\epsilon \over 2}\ \text{fuer alle } n \geq N
 $$
Mit der Dreiecksungleichung folgt
$$
 |a_n - a_m| \leq |a_n - a| + |a_m -a| < {\epsilon \over  2} + {\epsilon \over 2} = \epsilon
$$
fuer alle $n, m \geq N \blacksquare$

Daher ist jede Cauchyfolge in den [Reellen Zahlen](Reelle%20Zahlen.md) auch [Konvergent](Konvergenz.md).