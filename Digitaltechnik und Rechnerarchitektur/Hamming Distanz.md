
Sei $\alpha = a_{1} \dots a_{k}$ und $\beta = b_{1}, \dots, b_{k}$ Wörter die Hamming Distanz dieser Wörter ist definiert als:

$$\Delta_{H}(\alpha, \beta) := \sum\limits^{k}_{i=1} \delta(a_{i}, b_{i}) \text{ wobei } \delta(a, b):=
\begin{cases}
1 : \text{if } a\not = b \\
0 : \text{if } a = b
\end{cases}
$$

>[!NOTE] Die Hamming Distanz ist also gleich der Anzahl an Bits die die Zwei Wörter voneinander unterscheiden

Die Hamming Distanz eines Encodings ist definiert als der kleinste mögliche Abstand zwischen zwei Wörtern.

>[!IMPORTANT] Wir können $\Delta_{H}(\epsilon) - 1$ Fehler Erkennen

>[!IMPORTANT] Wir können $\frac{\Delta_{H}(\epsilon)-1}{2}$ Fehler Korrigieren
