
Wir Skalieren [B-Komplement](B-Komplement.md) Zahlen mit einem Festen Faktor $B^{-n}$. Verwenden wir $n$ Stellen nach dem Radix Punkt führt dies zu:

$$\langle[x_{m+n}, \dots, x_0]\rangle^\mathbb R_{B, n} := \langle[x_{m+n}, \dots, x_0]\rangle^\mathbb Z_B \cdot B^{-n} = \alpha(x_{m+n}) \cdot B^m + \sum\limits^{m+n-1}_{i=0} x_i \cdot B^{i-n}$$

Arithmetische Operationen sind dieselben wie für [B-Komplement](B-Komplement.md) Zahlen. Nur bei der Multiplikation und Division müssen wir nach der Operation den Skalierten Faktor Korrigieren.

## Multiplikation

Bei der Multiplikation von $\langle P\rangle^\mathbb Z_B := \langle X \rangle^\mathbb Z_B \langle Y \rangle^\mathbb Z_B \cdot B^{-n}$ erhalten wir
$$\langle X\rangle^\mathbb R_{B,n} \cdot \langle Y\rangle^\mathbb R_{B,n} = \langle X\rangle^\mathbb R_{Z,n} \cdot B^{-n} \cdot \langle Y\rangle^\mathbb Z_{B,n} \cdot B^{-n} = \langle P\rangle^\mathbb R_{B,n}$$

Nach der Berechnung von $\langle X\rangle^\mathbb Z_{B,n} \cdot \langle Y\rangle^\mathbb Z_{B,n}$ mit der B-Komplement Multiplikation Shiften wir das Ergebnis um $n$ Stellen nach Rechts, wir löschen die letzten $n$ Stellen.

---

Fixed Point Zahlen sind schneller zu berechnen als [[Floating-Point Zahlen]] dafür ist der Zahlenbereich den man darstellen kann klein.

