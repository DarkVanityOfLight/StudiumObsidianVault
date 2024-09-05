
Sind $X_1, X_2: \Omega \to \mathbb R$ zwei [Zufallsvariablen](Zufallsvariablen.md), dann ist die __Covarianz__ von $X_1$ und $X_2$
$$Cov(X_1, X_2) = E((X_1 - E(X_1)) \cdot (X_2 - E(X_2)))$$
Als Spezialfall erhalten wir die Varianz
$$V(X) = Cov(X, X)$$
Offenbar ist
$$Cov(X_1, X_2) = Cov(X_2, X_1)$$

für zwei [Zufallsvariablen](Zufallsvariablen.md) $X_1, X_2: \Omega \to \mathbb R$ gilt
$$Cov(X_1, X_2) = E(X_1 \cdot E(X_2)) - E(X_1) \cdot E(X_2)$$

für unabhängige Zufallsvariablen $X_1, X_2: \Omega \to \mathbb R$ist
$$Cov(X_1, X_2) = 0$$

Es ist 
$$V(X_1 + x_2) = V(X_1) + V(X_2) + 2 Cov(X_1, X_2)$$
