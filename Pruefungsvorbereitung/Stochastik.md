



$$\left(n \atop k \right) = \left( n\atop n -k\right)$$
$$(n+1)\left(n \atop k\right) = (k+1)\left(n+1 \atop k+1\right)$$
$$\sum^k_{j=0} \left(n \atop j\right) \left(m\atop k-j\right) = \left(n+m\atop k\right)$$
$$\left(n\atop k\right) = \frac{n!}{k!(n-k)!}$$
$$\left(n+1 \atop k+1\right) = \left(n\atop k\right) + \left(n\atop k+1\right)$$
$$\sum^n_{k=0} (-1)^k \left(n\atop k\right) = 0$$
$$|M_1 \cup \dots\cup M_n| = \sum^n_{k=1} (-1)^{k-1} \sum_{|T| = k} |M_T|$$

---

__Catalan Zahlen__
$$c_n = \frac{1}{n+1}\left( 2n \atop n\right)$$
__Stirlingzahl__
Stirlingzahl (zweiter Art) $S(n, m)$ die Anzahl der Partitionen einer n-elementigen
Menge in $m$ nichtleere Teilmengen.
$$\begin{align}
&S(n, m) = 0;S(n+1, m+1) = \sum^n_{k=m} \left(n \atop k\right) S(k, m)\\
\lor& S(n+1, m+1) = S(n, m) + (m+1) \cdot S(n, m+1)\\
\lor& S(n, m) = \frac{1}{m!} \sum^m_{k=0} (-1)^k \left(m \atop k\right) (m-k)^n
\end{align}$$

