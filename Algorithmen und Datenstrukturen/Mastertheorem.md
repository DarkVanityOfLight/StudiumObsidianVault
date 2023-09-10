
## Einfache Form

Sei $T$ eine Laufzeitfunktion, die die folgende Rekursionsungleichung erfüllt:

$$T(n) \le \left\lbrace\begin{align*}
&C &\text{für alle } n &\le n_{0}\\
&a \cdot T\left(\left\lceil\frac{n}{b}\right\rceil + e\right)+ Dn^{s}&\text{für alle } n &> n_{0}
\end{align*}\right.$$

Dann gilt:
1. Wenn $a > b^s$ (d.h. $\log_{b} a > s$), dann ist $T(n) \in O(n^{\log_{b} a})$
2. Wenn $a = b^{s}$(d.h. $log_{b} a = s$), dann ist $T(n) \in O(n^{s} \log n)$
3. Wenn $a <  b^{s}$(d.h. $\log_{b} a < s$), dann ist $T(n) \in O(n^{s})$

Diese Schranke ist scharf.


Sei $T$ eine Laufzeitfunktion, die die folgende Rekursionsungleiuchung erfüllt:

$$T(n) \leq \begin{cases}
C : n\leq n_0\\
a \cdot T(\lceil \frac{n}{b}\rceil + e) + Dn^s : n > n_0
\end{cases}$$

Dann gilt:

1. Wenn $a > b^s$(d.h $\log_b(a)> s$) dann ist $T(n)\in O(n^{\log_b a})$
2. Wenn $a = b^s$(d.h $\log_b(a) = s$) dann ist $T(n) \in O(n^s \log n)$
3. Wenn $a < b^s$(d.h $\log_b(a) < s$) dann ist $T(n) \in O(n^s)$


## Beispiel

Laufzeit von Merge Sort

$T(1) = c$
$T(n) \leq 2 \cdot T(\frac{n}{2} + 1) + dn$ für $n>2$

Nach dem 2. Fall des Mastertheorems:
$T(n) \in O(n\log n)$

