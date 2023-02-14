Sei $K$ ein [Angeordneter Körper](Angeordneter%20Körper.md). Eine [Folge](Mathe/Folgen.md) heißt Cauchyfolge, wenn es zu jedem $\epsilon > 0$ ein $N \in \mathbb N$ gibt mit 
$$
|a_n - a_m| < \epsilon\ \text{fuer alle } n,m \geq N
$$
Der Abstand zwischen den Folgegliedern wird also beliebig klein.

Jede Cauchyfolge ist [Beschränkt](Konvergenz.md#Beschränkt).

---

> Sei $K$ ein angeordneter [Körper](Körper.md). Jede [konvergente](Konvergenz.md) [Folge](Mathe/Folgen.md) ist eine Cauchyfolge.

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

Sei $(a_n)$ eine Folge in einem [Archimedischen Koerper](Körper.md#Archimedisch). Gibt es ein $0 < \lambda < 1$ mit $$|a_{n+1} - a_n| \leq \lambda|a_n -a_{n-1}|$$
für alle $n$, so ist $(a_n)$ eine Cauchyfolge.

---

> Jeder unendliche Dezimalbruch ist eine Cauchyfolge


Die Menge der Cauchyfolgen in $\mathbb Q$ ist ein kommutativer Ring mit $1$.
Ist $a_{n}$ eine Cauchyfolge die keine [Nullfolge](Nullfolge.md) ist, und $a_{n}\not = 0$ für alle $n$, dann ist $\frac{1}{a_{n}}$ eine  Cauchyfolge.

Ist $(a_n)$ eine Cauchyfolge, die keine [Nullfolge](Nullfolge.md) ist, und mit $a_{n}\not = 0$ für alle $n$, dann gibt es ein $C > 0$ mit $|a_{n}| \ge C$ für alle $n\in N$

Ist $(a_{n})$ eine Cauchyfolge, die keine [Nullfolge](Nullfolge.md) ist, dann sind nur endlich viele $a_{n} = 0$

---

Jede Cauchyfolge in $\mathbb R$ ist konvergent.
