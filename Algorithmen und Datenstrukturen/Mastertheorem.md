
## Einfache Form

Sei $T$ eine Laufzeitfunktion, die die folgende Rekursionsungleichung erfüllt:

$$T(n) \le \left\lbrace\begin{align*}
&C &\text{für alle } n &\le n_{0}\\
&a \cdot T\left(\left\lceil\frac{n}{b}\right\rceil + e\right)+ Dn^{s}&\text{für alle } n &> n_{0}
\end{align*}\right.$$

Dann gilt:
1. Wenn $a > b^s$ (d.h. log $\log_{b} a > s$), dann ist $T(n) \in O(n^{\log_{b} a})$
2. Wenn $a = b^{s}$(d.h. $log_{b} a = s$), dann ist $T(n) \in O(n^{s} \log n)$
3. Wenn $a <  b^{s}$(d.h. $\log_{b} a < s$), dann ist $T(n) \in O(n^{s})$
