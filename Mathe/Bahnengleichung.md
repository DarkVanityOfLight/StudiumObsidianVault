Wir betrachten nun wieder die Operation einer [Gruppe](Gruppe.md) $G$ auf einer [Menge](Mengen.md) $M$ und fragen nach der Beziehung zwischen der [Bahn](Bahn.md) eines Elements $m\in M$ und dem [Stabilisator](Bahn.md#Stabilisator) von $m$.

Sei 
$$G\times M \to M$$
eine Operation, $m\in M$ und
$H:= Stab(m)$.
Dann gibt es eine natürliche [Bijektion](Bijektiv.md)
$$\begin{align}
&G/H \to Gm\\
gH \mapsto g \cdot m
\end{align}$$

## Bahnformel
Sei $G\times M \to M$ eine Operation und $m\in M$, Dann gilt 
$$
|Gm|\cdot |Stab(m)| = |G|.
$$

## Bahnengleichung
Sei $R\subset M$ ein vollständiges Repräsentantensystem der [Bahnen](Bahn.md) einer Operation $G\times M \to M$. Dann gilt
$$\begin{align}
|M| = \sum\limits_{r\in R} \frac{|G|}{|Stab(r)|}
\end{align}$$
