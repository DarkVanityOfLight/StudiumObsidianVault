
Gegeben ist ein Punkt des gleichseitigen Dreiecks $D$, wir wollen untersuchen, auf welche anderen Punkte dieser unter der Operation $$\text{Sym}(D) \times D \to D$$
abgebildet werden kann. Diese Menge nennt man die Bahn, die Anzahl der Elemente die Länge der Bahn, Beispiele von Bahnen sind:

![bahn](bahn.png)

Die Operation auf $D$ induziert eine Operation 
$$\text{Sym}(D) \times 2^D \to 2^D$$
auf der Menge aller Teilmengen von $D$. In der Bah der schwarzen Teilmenge liegt außerdem noch die weiße Teilmenge: 
![bahn2](bahn2.png)
Andererseits kann man die Menge aller Elemente von Sym($D$) betrachten, die einen gegebenen Punk (oder eine Teilmenge) festhalten. Die Ecke 1 wird festgehalten von $\{id, (2 \leftrightarrow 3)\}$, der Mittelpunkt $m$ von Sym ($D$) und der Punkt $p_1$ nur von der Identität. Die schwarze Teilmenge wird festgehalten von
![bahn2](bahn2.png)

Wir beobachten, dass diese Mengen stets Untergruppen von $Sym(D)$ sind, und das Produkt der Gruppenordnung mit der Länge der jeweiligen Bahn stets $|Sym(D)| = 6$ ergibt

| |Bahn|festgehalten von| |
|-|----|-----------------|-|
|1| $\{1, 2, 3\}$|$\{id, (2 \leftrightarrow 3)\}$|$3\cdot 2 = 6$|
|m|$\{m\}$| $Sym(D)$|$1\cdot 6 = 6$|
|$p_1$|$\{p_1,..., p_6\}$|$\{id\}$|$6\cdot 1$|

---
## Bahn
Sei $G\times M \to M$ eine Operation. Fuer $m \in M$ nennt man
$$Gm = \{g \cdot m|g\in G\}\subset M$$
die __Bahn__ oder den __Orbit__ von $m$.

## Stabilisator
Ist $N\subset M$ eine Teilmenge, dann heißt
$\text{Stab}(N) = \{g \in G|gN = N\}$ wobei $gN = \{g \cdot n|n\in N\}$, der __Stabilisator__ der Menge $N$ ist. Der wichtigste Spezialfall ist der Stabilisator einer einelementigen Menge: Fuer ein Element $m \in M$ sei
$$\text{Stab}(m) = \{g \in G | g\cdot m = m\} \cdot |Stab(m)|$$
Eines unserer zentralen Ziele ist der Beweis der Bahnformel:
Fuer jede Gruppenoperation $G\times M \to M$ und jedes $m\in M$ gilt
$|G| = |Gm| \cdot |Stab(m)|$.

---

Zwei Bahnen $Gm_1$ und $Gm_2$ sind entweder gleich oder [Disjunkt](Disjunkt.md). In der gleichen Bahn zu sein ist also eine [Äquivalenzrelation](Äquivalenzrelationen.md).

## Quotient
Die Menge der Bahnen bezeichnen wir mit $M/ G$ Quotient von $M$ nach $G$. Jedes Element $m\in Gm_1$ nennen wir einen Repräsentanten der Bahn, denn $Gm = Gm_1$. Weiter heisst
$$\begin{align}
\pi:& M \to M/ G\\
&m \mapsto Gm
\end{align}$$
Quotientenabbildung.

---

## Repräsentantensystem
Sei $G\times M \to M$ eine Operation. Ein vollständiges Repräsentantensystem der Bahn ist eine Teilmenge $R\subset M$, sodass jede Bahn $G_m$ genau ein Element von $R$ enthält.
Dann ist $M$ die disjunkte Vereinigung
$$M = \bigcup^{\cdot}_{r\in R} G\cdot r$$

Die Darstellung von Permutation in Abbildungsschreibweise ist nicht effizient: Fuer die Permutation 

$$
\sigma = \left(\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9\\
2 & 3 & 1 & 4 & 5 & 6 & 7 & 8 & 9
\end{matrix}\right)
$$
müssen wir uns die Bilder von $4, ..., 7$ nicht merken. Die Bilder von $1, 2, 3$ können wir in dem Diagramm 
![zykel](zykel.png)
codieren. Dies ist die Idee eines Zykels

## Zykel

Ist $\sigma \in S_n$ dann zerlegt die Operation von $\langle \sigma \rangle$ die Menge $\{1, ..., n\}$ in Bahnen der Form 
$$\langle \sigma\rangle x = (x, \sigma(x), \sigma^{2}(x), ..., \sigma^{t-1}(x))$$
das heißt wir codieren zusätzlich zu der Bahn als Menge noch die Reihenfolge in der die Bahn durchlaufen wird. [Transposition](Gruppe.md#Transposition) sind Zykel der  Länge $2$. Fuer das neutrale Element schreiben wir $()$. Man könnte fuer Zykel auch eine Kreisnotation wie oben verwenden, die würde aber zu viel Platz verbrauchen und ist auch in einer Computerkonsole schwer einzugeben.
Transpositionen sind Zykel der Länge 2

### Beispiel

$$\sigma = \left(\begin{matrix}1 & 2& 3& 4\\ 1 & 3& 4&2\end{matrix}\right) = (2, 3, 4)$$
$$\{1, ..., 4\} = \{1\} \cup \{2, 3, 4\}$$

$$\begin{align}\sigma^2 =& (2, 3, 4) \circ (2, 3, 4)\\
=& (2, 4, 3)
\end{align}$$

---

1. Jedes Element der $S_n$ ist Produkt elementfremder Zykel
2. Jedes Element der $S_n$ ist Produkt von Transpositionen

$$\sigma: <\sigma> x_i \to <\sigma> x_i$$

$$\sigma: \{1, 2, 3\} \to \{1, 2, 3\}$$
$$\sigma: \{4, 5\} \to \{4, 5\}$$
ist der Zykel $\sigma_i$
$\sigma = \sigma_1 \circ ... \circ \sigma_r$
