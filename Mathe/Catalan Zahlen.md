
Für $n\in \mathbb N_0$ ist die Catalan Zahl $c_n$ die Anzahl der vollständigen Klammerungen eines Produkts $x_1 \cdot ... \cdot x_{n+1}$ aus $n+1$ Faktoren.

Offenbar gilt $c_0 = 1, c_1 = 1$  und $c_2 = 2, c_3 = 5$. über die folgende Rekursionsgleichung können wir alle $c_n$ berechnen:

Es gilt $c_0 = 1$ und
$$c_n = \sum^{n-1}_{j=0} c_j c_{n - 1 - j}$$
für $n \ge 1$.

---

>[!SATZ]
>Es gibt eine Bijektion zwischen der Menge der vollstaendigen Klammerungen von $x_1 \cdot ... \cdot x_{n+1}$ und der Menge der kuerzesten, ueberhalb der Winkelhalbierenden verlaufenden Wege in einem $(n+1) \times (n+1)$ Gitter 

Diese Anzahl an Wegen kann auch folgendermassen geschrieben werden:
$$\frac{n+1 - m}{n+1}\left( n+m \atop m \right)$$
Siehe [Aufgabe 1](Blatt%202.md#Aufgabe%201).

---

Es gilt direkt aus dem oberen mit $n = m$
$$c_n =  \frac{1}{n+1} \left(2n \atop n\right)$$


