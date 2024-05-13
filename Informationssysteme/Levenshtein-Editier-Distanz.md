Die Levenshtein-Editier-Distanz zwischen zwei Strings $x$ und $y$ ist die minimale Anzahl von Änderungsoperationen(insert, replace, delete), die benötigt werden um $x$ in $y$ zu transformieren.

Die minimale Anzahl an Operationen $m[i, j]$, um die Praefix-Zeichenkette $x[1:i]$ in $y[1:j]$ zu transformieren ist definiert durh
$$m[i, j] = \min\begin{cases}
m[i-1, j-1]+ (x[i] = y[j]?0:1)\qquad (\text{ersetze } x[i])\\
m[i-1, j]+1 \qquad \text{loesche }x[i]\\
m[i, j-1]+1\qquad \text{fuege ein }y[i]
\end{cases}$$

