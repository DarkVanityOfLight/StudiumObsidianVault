Angenommen $\sigma$ besitzt mindestens ein Konstantensymbol

>[!DEFINITION]
>Eine __Herbrand-Struktur__ $\mathcal H = (D, I)$ erfüllt Folgendes:
>1. $D$ ist das __Herbrand-Universum__ aller $\sigma$ [Grundterme](Grundterme.md)
>2. $I(c) = c$, für jedes Konstantensymbol $c$
>3. $I(f)(t_1, \dots, t_n) = f(t_1, \dots, t_n)$ für jedes $n$-stellige Funktionssymbol $f$ und alle Grundterme $t_1, \dots, t_n$.

Eine Herbrand-Struktur ist daher eine "syntaktische" Struktur, deren Funktionssymbole "als sich selbst" interpretiert werden.


>[!NOTE] Proposition
>Der Wert $\textbf{t}$ von $t$ in einer Herbrand-Struktur ist $t$

>[!DEFINITION] überführungslemma für Herbrand-Strukturen
> Es gilt, dass
> $$(\mathcal H, \nu) \vDash \varphi[t/x] \text{ g.d.w } (\mathcal H, \nu[t/x]) \vDash \varphi$$

