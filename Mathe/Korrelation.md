
Das Problem der [Covarianz](Covarianz.md) liegt darin, dass unklar ist, was der eigentliche Zahlenwert bedeutet. Wir müssen ihn relativ zu einer anderen Zahl sehen. Man vergleicht die Covarianz mit den Produkt der Standardabweichung der Zufallsvariablen:

Sind $X_1, X_2: \Omega \to \mathbb R$ [Zufallsvariablen](Zufallsvariablen.md) mit positiver [Varianz](Varianz.md), dann ist die __Korrelation__ von $X_1$ und $X_2$
$$Corr(X_1, X_2) = \frac{Cov(X_1, X_2)}{\sigma(X_1) \cdot \sigma(X_2)}$$
Da die Varianz positiv ist, ist sichergestellt das der Nenner nicht $0$ ist. Für die Korrelation erhalten wir dann:
$$-1 \le Corr(X_1, X_2) \le 1$$
eine $Corr(X_1, X_2) > 0$ heißt $X_1$ und $X_2$ korreliert, falls $Corr(X_1, X_2) < 0$ dann antikorreliert.

---

Sei $X$ eine Zufallsvariable mit positiver Varianz $a, b \in\mathbb R$ mit
$a\not = 0$. Dann ist
$$Corr(X, a\cdot X + b) = sgn(a) =\begin{cases}1 \quad\text{falls } a > 0 \\ -1 \quad\text{falls } a < 0\end{cases}$$

für Zufallsvariablen $X_1$ und $X_2$ und $a, b\in\mathbb R$ ist 
$$Cov(X_1, a \cdot X_2 + b) = a\cdot Cov(X_1, X_2)$$
und falls $X_1$ und $X_2$ positive Varianz haben und $a\not = 0$ ist haben wir 
$$Corr(X_1, a\cdot X_2 + b) = sgn(a) \cdot Corr(X_1, X-2)$$


---

für [Zufallsvariablen](Zufallsvariablen.md) $X_1$ und $X_2$ mit positiver [Varianz](Varianz.md) gilt
$$|Corr(X_1, X_2)| = 1$$
genau dann, wenn es $a, b, c\in\mathbb R$ gibt mit $a, b$ nicht beide $0$ und
$$a\cdot X_1 + b\cdot X_2 + c\sim 0$$
