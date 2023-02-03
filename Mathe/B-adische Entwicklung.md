Um [Natürliche Zahlen](Natürliche%20Zahlen.md) im Computer zu repräsentieren, verwendet man typischerweise die Binärentwicklung, d.h. die Darstellung der Zahl durch eine [Summe](Summe%20und%20Produkt.md) von [Potenzen](Potenz.md) der Basis $B=2$. Allgemeiner hat man für beliebige Basen $B \ge 2$:

Für jedes $B \in \mathbb Z, B\geq 2$ ist die Abbildung $$\begin{align}
\phi_{B, r}:& \{0, ..., B-1\}^r &\to& \{0, ..., B^r - 1\}\\
&(a_{r-1, ... a_0}) &\mapsto& \sum^{r-1}_{i=0} a_iB^i
\end{align}$$
bijektiv. Für $n \in \{0, ..., B^{r-1}\}$ heißt $\phi^{-1}_{B, r}(n)$ die B-adische Entwicklung mit $r$ Stellen von $n$
 
## Beispiel
Im Dezimalsystem ($B=10$) gilt
$$\phi_{10, 3}((0, 2, 3)) = 0 \cdot 10^2 + 2 \cdot 10 + 3 \cdot 10^0 = 23$$
und im Binärsystem($B=2$)
$$
\phi_{2, 8}((0, 0, 0, 1, 0,1, 1, 1)) = 1 \cdot 2^4 + 0 \cdot 2^3 + 1\cdot 2^2 + 1\cdot 2^1 + 1\cdot 2^0 =23
$$
Siehe [Aufgabe 3](GDP%201.md#Aufgabe%203)


## Division mit Rest
Für gegebenes $(a_{r-1}, ..., a_0)$ ist es also leicht das [Bild](Abbildungen.md#Bild) unter $\phi_{B, r}$ zu berechnen. Zum Beweis des Satzes verwenden wir einen Algorithmus, der das umgekehrte Problem löst, d.h. zu einer gegebenen Zahl $n$ die B-adische Entwicklung $\phi^{-1}_{B,r}(n)$ bestimmt. Die Basis des Algorithmus ist die [Division mit Rest](Division%20mit%20Rest.md)

$$\begin{align}
&n=23 \qquad &B=10 \qquad &123 = 12 \cdot 10 &+ 3\\
&&& 12 = 1 \cdot 10 &+2\\
&&& 1 = 0 \cdot 10 &+ 1
\end{align}$$
