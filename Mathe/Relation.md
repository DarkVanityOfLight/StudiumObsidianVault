Eine Relation zwischen [Mengen](Mengen.md) $M$ un $N$ ist gegeben durch eine [Teilmenge](Teilmengen.md) $R\subset M\times N$

Wir können eine Relation $R\subset M\times N$ mit der Aussageform $(m, n) \in R$ identifizieren. Fuer diese schreiben wir dann üblicherweise $m\square n$

## Beispiel 1.1
$M = \{2,3,7\}$, $N=\{4,5,6\}$

$$\begin{align}
R &= \{(m,n) \in M \times N | \text{m teilt n}\}\\
&= \{(2,4), (2,6), (3,6)\}
\end{align}$$

Sei $M$ eine Menge. Eine Relation $R \subset M \times M$ auf $M$ heißt:
- Reflexiv, wenn $(m, m) \in R$ fuer alle $m \in M$
- Transitiv, wenn $(l, m) \in R$ und $(m, n) \in R \implies (l, n) \in R$
- Antisymmetrisch, wenn $(n, m) \in R$ und $(m, n) \in R \implies m = n$

Sind alle diese Punkte erfüllt nennt man die Relation [Halbordnung](Halbordnung.md).
Gilt zusätzlich noch für all $m, n \in M$, dass $(m, n) \in R$ oder $(n, m) \in R$, so heißt $R$ [Totalordnung](Totalordnung.md)


## Beispiel 1.2
$M$ Menge, Inklusion $\subset$ auf $2^M$
[Halbordnung](Halbordnung.md) auf $2^M$

- Reflexiv: $A\subset A \forall A \subset M$
- Transit: $A\subset B$ und $B\subset C \implies A \subset C$
- Antisym: $A\subset B$ und $B \subset A \implies A = B$

