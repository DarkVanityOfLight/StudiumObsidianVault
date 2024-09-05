
Eine Zahlpartition von $n \in\mathbb N_0$ ist eine Darstellung von $n$ als Summe positiver ganzer Zahlen. Dabei sehen wir zwei Gleichungen
$$n = p_1 + \dots p_n$$
als äquivalent an, wenn sie durch das [Kommutativgesetz](Kommutativgesetz.md) auseinander hervorgehen.

Wir bezeichnen mit $P(n, m)$ die Anzahl aller Partitionen von $n$ in $m$ Zahlen. Die Anzahl aller Partitionen von $n$ ist
$$P(n) = \sum^n_{m=0} P(n, m)$$

Wie beim Abzaehlen von [Partition von Mengen und Relationen](Partition%20von%20Mengen%20und%20Relationen.md) gilt
$$P(0, 0) = 1$$
denn die leere Summe gibt $0$. Ebenso ist
$$\begin{align}
P(n, 0) = 0 \quad\text{fuer } n > 0\\
P(0, m) = 0\quad\text{fuer } m > 0
\end{align}$$
Eine Berechnung von $P(n, m)$ aus $S(n, m)$ ist nicht ohne Weiteres möglich. Wir wissen jedoch es gilt
$$S(n, m) \le P(n, m)$$
denn jede Mengenpartition gibt eine Zahlpartition.

In einer Zahlpartition kann man annehmen, dass die $p_i$ absteigend sortiert sind.
Die Sortierten Listen koennen wir als Young-Diagramm darstellen.

Daher gilt für $n < m$
$$P(n, m) = 0$$
und für alle $n \ge m \ge 0$ gilt

$$
P(n + 1, m+1) = P(n -m, m+1) + P(n, m)
$$

## Geordnete Zahlpartitionen

Eine geordnete Zahlpartition von $n\in\mathbb N$ ist eine Liste $P = (p_1, \dots, p_m) \in \mathbb N^m$ sodass
$$n = p_1 + \dots + p_m$$
Es ist also $p_i \ge 1$. Im Fall $n=0$ haben wir wieder wie im ungeordneten Fall die leere Summe.
Für $n, m \in\mathbb N$ gibt es genau
$$\left( n-1 \atop m-1\right)$$
geordnete Partitionen von $n$ in $m$ Zahlen.
Daraus folgt, eine Zahl $n\in\mathbb N$ hat genau $2^{n-1}$ geordnete Partitionen.

---

Für $n, m \in\mathbb N$ gibt es genau
$$\left( n+m-1 \atop m-1\right)$$
Listen $(p_1, \dots, p_m) \in \mathbb N^m_{0}$ mit
$$n = p_1 + \dots + p_m$$

