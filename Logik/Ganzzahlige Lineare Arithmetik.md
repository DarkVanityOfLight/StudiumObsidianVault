
Dies bezeichnet die [Theorie](Theorien%20der%20ersten%20Stufe.md) von $(\mathbb N; +, 1, 0)$.

Folgendes ist Presburgers Axiomatisierung von $(\mathbb N; +, 1, 0)$ 
1. $\forall x \neg(x+1 = 0)$
2. $\forall x(x +0 = x)$
3. $\forall x, y(x+1 = y+1 \to x = y)$
4. $\forall x, y(x + (y+1) = (x+y) + 1)$
5. $\forall x, y(x+(y+1) = (x+y)+1)$
6. $\varphi(0) \land \forall x(\varphi(x) \to \varphi(x+1)) \to \forall x\varphi(x)$ für jede FO-Formel $\varphi$ mit einer freien Variable

Wir betrachten $(\mathbb Q; <, +, 0, 1)$. Der Bequemlichkeit halber fuegen wir Konstanten hinzu, 
$$c (c\in \mathbb Q)$$
die "als sich selbst" interpretiert werden, und zudem unaere Funktionssymbole
$$c. (c\in\mathbb Q)$$
die als "Multiplikation mit diesem Koeffizienten" interpretiert wird:
$$c. : n\mapsto c.n$$
Die resultierende [Theorien der ersten Stufe](Theorien%20der%20ersten%20Stufe.md) wird als $Th(\mathcal Q_+)$ bezeichnet.

>[!THEOREM]
>$Th(\mathcal Q_+)$ hat [Quantorenelemination](Quantorenelemination.md), daher ist sie vollständig und entscheidbar

## Normalformen für Atome

Wir lassen generelle lineare (Un)Gleichung als [Atome](Logik/Atom.md) zu
$$t_1 \sim t_2, \qquad \sim \in \lbrace <, >, =\rbrace$$
wobei jede (Un)Gleichungsseite($t_i$) die folgende Form hat
$$c_1 x_1 + \dots c_nx_n + c_0$$
wobei die Variablen $x_i$'s paarweise verschieden sind.
Jedes solcher Atome lässt sich weiter vereinfachen zu:
$$t_1\sim 0, \qquad \sim\in\lbrace <,>,=\rbrace$$
