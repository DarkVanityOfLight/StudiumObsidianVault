
Für $n, m\in\mathbb N_0$ sei die Stirlingzahl (zweiter Art) $S(n, m)$ die Anzahl der [Partitionen](Partition.md) einer $n$-elementigen [Menge](Mengen.md) in $m$ nicht leere [Teilmengen](Teilmengen.md). Man schreibt auch $S(N, m)$ für die Menge der Partitionen von $N$ in $m$ Teilmengen.

Die Anzahl aller Partitionen einer $n$ elementigen Menge ist die __Bellsche Zahl__

$$B_n = \sum^n_{m=0} S(n, m)$$

Die Anzahl aller [Äquivalenzrelationen](Äquivalenzrelationen.md) auf einer $n$ elementigen Menge ist $B_n$.

Es gilt 
1. $S(0, 0) = 1$
2. $S(n, 0) = 0$ für $n > 0$

für alle $n < m$ gilt 
$$S(n, m) = 0$$
und für alle $n \ge m$ gilt
$$S(n+1, m+1) = \sum^n_{k=m} \left(n \atop k\right) S(k, m)$$

Für die Bellschen Zahlen $B_n$ gilt $B_0 = 1$ und
$$B_{n+1} = \sum_{k=0}^n \left( n\atop k\right) B_k$$
für alle $n\ge 0$.

Für die Stirlingzahlen gilt
$$S(n+1, m+1) = S(n, m) + (m+1) \cdot S(n, m+1)$$
für alle $n, m \ge 0$.

Mit der Hilfe der Abzählung von [Geordnete Partitionen](Partition%20von%20Mengen%20und%20Relationen.md#Geordnete%20Partitionen) erhalten wir eine Geschlossene Form für die Stirlingzahlen:
$$S(n, m) = \frac{1}{m!} \sum^{m}_{k=0} (-1)^k \left( m\atop k\right) (m-k)^n$$
für alle $n, m\in \mathbb N_0$.


