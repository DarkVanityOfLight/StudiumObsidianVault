
>[!DEFINITION]
>Eine endliche Teilmenge $S\subseteq E_0$ heisst Schnitt von $E_0$ falls gilt:
>$$\forall i. \forall e, e'\in E_i.(e\in S\land e' \leq_i e \implies e' \in S)$$


## Vergleiche

Ein [Ereignis](Ereignis.md) $e\in S$ ist das späteste Ereignis des [Prozesses](Prozess.md) $p_i$ im Schnitt genau dann wenn $\forall e' \in E_i.(e' \in S \implies e' \leq_i e)$

Ein Schnitt $S_2$ heißt später als ein Schnitt $S_1$ gdw. $S_1\subseteq S_2$


## Konsistenter Schnitt

Eine endliche Teilmenge $S\subseteq E_0$ heißt konsistenter Schnitt von $E_0$, falls gilt $\forall e, e' \in E_0.(e\in S\land e'\leq_0 e\implies e'\in S)$

Der globale Zustand eines konsistenten Schnitts $S$ ist ein Tupel $z(S) = (p(S), n(S))$ mit:

- $p(S) = (p_1(e_1), p_2(e_2), \dots, p_n(e_n))$ wobei $p_i(e_i)$ den Zustand des Prozesses $p_i$ nach dem Ereignis $e_i$ bezeichnet und $e_i$ das jeweils späteste Ereignis des Prozesses $p_i$ in $S$ ist; falls es kein solches Ereignis gibt, bezeichnet $p_i(e_i)$ den Anfangszustand von $p_i$.
- $n(S)$ bezeichne die Menge der Sendeereignisse in $S$, deren zugehöriges Empfangsereignis nicht in $S$ liegt, d.h. die unterwegs befindlichen Nachrichten.
