Lineare Block Codes werden verwendet um die [Hamming Distanz](Hamming%20Distanz.md) zwischen Wörtern zu erhöhen.

>[!IMPORTANT] Alle Wörter in einem Block Code haben die selbe länge

## Generator Matrizen

Sei $B = \lbrace\beta_{1},\dots, \beta_{l}\rbrace$ die Basis für $\epsilon(\Sigma)$, dann existiert eine $l\times n$ Matrix $G$ welche den Code generiert.

$$
\underbrace{(a_{1}, \dots, a_{l})}_{\alpha} \cdot \underbrace{\begin{pmatrix} \gamma_{1,1} & \dots & \gamma_{1,n} \\ \vdots &  & \vdots \\ \gamma_{l,1} & \cdots & \gamma_{l,n} \\ \end{pmatrix}}_{G} = (b_{1}, \cdots, b_{n})
$$

wobei $\beta = (\gamma_{i,1}, \cdots, \gamma_{i,n})$
Matrix Multiplikation codiert einen gegebenen Vektor $(a_{1}, \cdots, a_{l})$ in einen Vektor mit grösserer Redundanz $(b_{1}, \cdots, b_{n})$

![lincode](lincode.png)

Die dazugehörige Matrix sieht so aus:

$$\left(\begin{array}{cccc|ccc}
1 & 0 & 0 & 0 & 1 & 1 & 0\\
0 & 1 & 0 & 0 & 1 & 0 & 1\\
0 & 0 & 1 & 0 & 1 & 1 & 1\\
0 & 0 & 0 & 1 & 0 & 1 & 1
\end{array}\right)$$

Die Linke Seite der Matrix $G$ ist die Einheitsmatrix $\mathbb{I}_l$.

Die Rechte Seite liest man aus der Tabelle ab indem man die Wörter aus der Einheitsmatrix abliest und die Kontrollbits aufschreibt.

Code Wörter bestehen deshalb aus einer Verbindung von Datenbits und Kontrollbits.

## Kontroll Matrix

Zu jeder Generator Matrix $G = (\mathbb{I}_L | P)$ definieren wir die Kontroll Matrix als $H := (P^T \mathbb{I}_{n-l})$.

Wir Prüfen nun auf Fehler indem wir das Code Wort mit der Kontrollmatrix Multiplizieren.

Wenn es nur einen Fehler gibt dann ist das Ergebnis die Spalte des Fehlers in $H$

### Beispiel

Das Wort $0001011$ hat einen Fehler: $0001111$


$$\left(\begin{array}{cccc|ccc}
1 & 1 & 1 & 0 & 1 & 0 & 0\\
1 & 0 & 1 & 1 & 0 & 1 & 0\\
0 & 1 & 1 & 1 & 0 & 0 & 1\\
\end{array}\right) 
\begin{pmatrix}
0\\0\\0\\1\\1\\1\\1
\end{pmatrix} = \begin{pmatrix}1\\0\\0\end{pmatrix}$$

Die 5. Spalte Entspricht dem Ergebnis, also ist das 5 Bit der Fehler im Code Wort
