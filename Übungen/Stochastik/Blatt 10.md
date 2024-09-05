
> Kris Grohe, Kilian Lichtner

## Aufgabe 1

$$\begin{align}
Cov(X_1, X_2) =& E\big(( (X_1 - E(X_1)) \cdot (X_2 - E(X_2)) \big)\\
\iff& E(X_1 X_2 - X_1 E(X_2) - X_2 E(X_1) + E(X_1) E(X_2)) &|\text{2.6.13}\\
\iff& E(X_1 X_2) - E(X_1 E(X_2)) - (X_2 E(X_1)) + E(E(X_1)E(X_2)) &|\text{2.6.14}\\
\iff& E(X_1 X_2) - E(X_2) E(X_1) - E(X_1) E(X_2) + E(X_1) E(X_2)\\
\iff& E(X_1 X_2) - E(X_2) E(X_1)\\
&&\blacksquare
\end{align}$$

## Aufgabe 2

Nach dem Deduktionssatz ist zu zeigen:
$$P(A|B) = P(A) \vdash P(B|A) = P(B)$$
Da $\frac{P(A\cap B)}{P(B)} = P(A)$ gilt muss $P(A\cap B) = P(A) \cdot P(B)$ gelten, denn dann
$$\frac{P(A) \cdot P(B)}{P(B)} = \frac{1 \cdot P(A)}{1} = P(A)$$

Betrachten wir nun also $P(B|A)$, per Definition von $P(B|A)$
und nach der Oben gezeigten Bedingung $P(A\cap B) = P(B \cap A) = P(A) \cdot P(B)$
$$\begin{align}
&\frac{P(B\cap A)}{P(A)}\\
\iff&\frac{P(B) \cdot P(A)}{P(A)} = \frac{1\cdot P(B)}{1} = P(B)\\
&&\blacksquare
\end{align}$$


## Aufgabe 3

| $X_1$ | $X_2$ | $(X_1 + X_2)$ | $(X_1 - X_2)$ | $(X_1 + X_2) \cdot (X_1 - X_2)$ |
| ----- | ----- | ------------- | ------------- | ------------------------------- |
| 1     | 1     | 2             | 0             | 0                               |
| 1     | 2     | 3             | -1            | -3                              |
| 1     | 3     | 4             | -2            | -8                              |
| 1     | 4     | 5             | -3            | -15                             |
| 1     | 5     | 6             | -4            | -24                             |
| 1     | 6     | 7             | -5            | -35                             |
| 2     | 1     | 3             | 1             | 3                               |
| 2     | 2     | 4             | 0             | 0                               |
| 2     | 3     | 5             | -1            | -5                              |
| 2     | 4     | 6             | -2            | -12                             |
| 2     | 5     | 7             | -3            | -21                             |
| 2     | 6     | 8             | -4            | -32                             |
| 3     | 1     | 4             | 2             | 8                               |
| 3     | 2     | 5             | 1             | 5                               |
| 3     | 3     | 6             | -6            | 0                               |
| 3     | 4     | 7             | -1            | -7                              |
| 3     | 5     | 8             | -2            | -16                             |
| 3     | 6     | 9             | -3            | -27                             |
| 4     | 1     | 5             | 3             | 15                              |
| 4     | 2     | 6             | 2             | 12                              |
| 4     | 3     | 7             | 1             | 7                               |
| 4     | 4     | 8             | -8            | 0                               |
| 4     | 5     | 9             | -1            | -9                              |
| 4     | 6     | 10            | -2            | -20                             |
| 5     | 1     | 6             | 4             | 24                              |
| 5     | 2     | 7             | 3             | 21                              |
| 5     | 3     | 8             | 2             | 16                              |
| 5     | 4     | 9             | 1             | 9                               |
| 5     | 5     | 10            | 0             | 0                               |
| 5     | 6     | 11            | -1            | -11                             |
| 6     | 1     | 7             | 5             | 35                              |
| 6     | 2     | 8             | 4             | 32                              |
| 6     | 3     | 9             | 3             | 27                              |
| 6     | 4     | 10            | 2             | 20                              |
| 6     | 5     | 11            | 1             | 11                              |
| 6     | 6     | 12            | 0             | 0                               |


Wir erhalten $P(Y = 0) = \frac{6}{36}$ und für jedes andere $$\begin{align}
Y \in&\\ &\lbrace -35, -32, -27, -24, -21, -20, -16, -15, -12, -11, -9,\\& -8, -7, -5, -3, 3, 5, 7, 8, 9, 11, 12, 15, 16, 20, 21, 24, 27, 32, 35\rbrace
\end{align}$$ erhalten wir $P(Y) = \frac{1}{36}$.


_b)_

Die Covarianz berechnet sich wiefolgt:
$$\begin{align}
Cov(X_1 + X_2, X_1 - X_2) =& E((X_1 + X_2) \cdot (X_1 - X_2)) - E(X_1 + X_2)E(X_1 - X_2)\\
&E(X_1^2 - X_2^2) - E(X_1 + X_2)E(X_1 - X_2)
\end{align}$$
für die Erwartungswerte gilt
$$\begin{align}
&E(X_1) = E(X_2) = \frac{1 + 2 + 3 +4 + 5+ 6}{6} = \frac{21}{6}\\
&E(X_1) + E(X_2) = E(X_1 + X_2) = 7\\
&E(X_1) - E(X_2) = E(X_1 - X_2) = 0\\
&E(X_1^2 - X_2^2) = 0
\end{align}$$


dann:
$$Cov(X_1 + X_2, X_1 - X_2) = 0 - 7 \cdot 0 = 0
$$

## Aufgabe 4
Nehmen wir an der Spieler Wählt Tür $1$
![Drawing 2024-07-02 14.54.26.excalidraw](Drawing%202024-07-02%2014.54.26.excalidraw.md)

