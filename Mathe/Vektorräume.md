Sei $K$ ein Körper. Ein $K$-Vektorraum ist eine Menge $V$ zusammen mit zwei Verknüpfungen:
$$\begin{align*}
V\times V \to V\\
(v, w) \mapsto   v+ w
\end{align*}$$
$$\begin{align*}
K\times V \to V\\
(\lambda, v) \mapsto \lambda \cdot v
\end{align*}$$
die folgenden Axiomen genuegen:

1. $(V, +)$ ist eine abelsche Gruppe
2. Assoziativgesetz $$\lambda \cdot (\mu \cdot v) = (\lambda \cdot \mu) \cdot v$$ für alle $\lambda, \mu \in K$ und $v\in V$,
3. $1\cdot v = v$ für alle $v\in V$,
4. Distributivgesetz $$\begin{align*}
(\lambda + \mu) \cdot v &= \lambda \cdot v + \mu \cdot v\\
\lambda \cdot (v+w) &= \lambda \cdot v + \lambda \cdot w
\end{align*}$$ für alle $\lambda, \mu \in K$ und $v, w \in V$

Die Elemente eines Vektorraums nennen wir auch Vektoren. Man beachte, dass hier $+$ sowohl für die Addition in $K$ als auch in $V$ verwendet wird, und $\cdot$ sowohl für die Multiplikation in $K$ als auch die Skalarmultiplikation. Welche der beiden Möglichkeiten gemeint ist, ist aber aus dem Typ der verknüpften Elemente klar.

Sei $V$ ein $K$-Vektorraum. Dann gilt 

$$\begin{align*}
0_{K} \cdot v &= 0_{V} \forall v\in V\\
\lambda \cdot 0_{V} &= 0_{V} \forall \lambda \in K\\
(-1) \cdot v &= -v \forall v \in V\\
\lambda \cdot v &= 0 \implies \lambda = 0 \lor v = 0 \forall \lambda \in K, v\in V
\end{align*}$$
Dabei bezeichnet $0_K$ das Neutrale von $(K, +)$ und $0_{V}$ das Neutrale von $(V, +)$. Ist aus dem Kontext klar, ob die Konstante $0_K$ oder der Nullvektor $0_{V}$ gemeint ist, schreiben wir einfach $0$.



## R-Modul
Man könnte $K$ in der Definition von $V$ durch einen kommutativen Ring $R$ mit $1$ ersetzen (z.B. $\mathbb Z$ oder einen [Polynomring](Polynomring.md)). Dann spricht man von einem __R-Modul__. Die Strukturtheorie von Moduln ist wesentlich komplizierter als die von Vektorräumen. Ein wesentlicher Grund hierfür liegt darin, dass die Aussagen oben im Allgemeinen nicht mehr korrekt ist. 

## Untervektorraum 
Sei $V$ ein $K$-Vektorraum. eine nicht leere Teilmenge $U\subset V$ heißt Untervektorraum, wenn
$$\begin{align*}
u_{1}, u_{2} \in U \implies u_{1} + u_{2} \in U\\
\lambda \in K, u\in U \implies \lambda \cdot u \in U
\end{align*}$$

 $U$ mit der von $V$ induzierten Addition und Skalarmultiplikation ist ein $K$-Vektorraum
 Jeder Untervektorraum $U$ enthält die $0\in V$(denn es gibt ein $u\in U$ und $0 = 0\cdot u\in U$).

Die Lösungsmenge eines [homogenen](Polynome.md#Homogenitaet) linearen Gleichungssystems für $x_{1}, ..., x_{n}$ über dem Körper $K$ ist ein Untervektorraum von $K^{n}$
 

## Vorkurs
Sei $n \in N$ eine natürliche Zahl.
Betrachte die Menge $R^n = R \times ... \times R$ aller n-Tupel von [reelle Zahlen](Reelle%20Zahlen.md)
$$R^n = \left\{ \underline x = \left(
\begin{array}. x_1 \\ \vdots \\ x_2\end{array} \right) | x_1 \in R,...x_n\in R\right\}$$

## Addition
$$\underline x  = \left(\begin{array}. x_1 \\ \vdots \\x_n \end{array} \right) \in R^n\ und\ \underline y = \left(\begin{array}. y_1 \\ \vdots \\y_n \end{array} \right) \in R^n$$
$$\underline x + \underline y := \left( \begin{array}. x_1 + y_1 \\ \vdots \\ x_n + y_n \end{array} \right) \in R^n$$
![vektoraddition](vektoraddition.png)
## Skalarmultiplikation
$$\underline x = \left(\begin{array}. x_1 \\ \vdots \\x_n \end{array} \right) \in R^n\ und\ \lambda \in R$$
$$\lambda \cdot \underline x := \left( \begin{array}
. \lambda\cdot x_1 \\ \vdots \\ \lambda \cdot x_n
\end{array}\right)$$
![skalarmultiplikation](skalarmultiplikation.png)