Sei $K$ ein [Angeordneter Körper](Angeordneter%20Körper.md). Eine [Folge](Folgen.md) heißt Cauchyfolge, wenn es zu jedem $\epsilon > 0$ ein $N \in \mathbb N$ gibt mit 
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
für alle $n, m \geq N \blacksquare$

Daher ist jede Cauchyfolge in den [Reellen Zahlen](Reelle%20Zahlen.md) auch [Konvergent](Konvergenz.md).

---

Sei $(a_n)$ eine Folge in einem [Archimedischen Körper](Mathe/Archimedischer%20Körper). Gibt es ein $0 < \lambda < 1$ mit $$|a_{n+1} - a_n| \leq \lambda|a_n -a_{n-1}|$$
für alle $n$, so ist $(a_n)$ eine Cauchyfolge.
