Um eine gute Schranke zu erhalten, ist es nicht ausreichend nur die [Varianz](Varianz.md) zu betrachten, man verwendet alle [Momente](Varianz.md#Momente) $E(X^i)$
fuer $i\in\mathbb N$. Alle Potenzen von $X$ kann man in der [Exponentialfunktion](Exponentialfunktion.md) codieren: Wir setzen $\lambda\in \mathbb R$
$$M_X(\lambda) = E(exp(\lambda \cdot X))$$
Im Allgemeinen muss dieser Erwartungswert nicht existieren

---

Sind $X_1, \dots, X_n$ unabhängige Zufallsvariablen, die Werte im Intervall $[a, b]$ annehmen, dann ist für alle $\epsilon > 0$
$$P(\frac{1}{n} \sum_{i=1}^n (X_i - E(X_i)) \ge \epsilon) \le exp(-\frac{2n}{(b-a)^2}) \epsilon^2$$
und
$$P(\frac{1}{n} \sum^n_{i=1} (X_i - E(X_i)) \le -\epsilon) \le exp(-\frac{2n}{(b-a)^2} \epsilon^2)$$