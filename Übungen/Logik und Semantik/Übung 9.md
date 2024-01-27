> Marcel Wirdel, Kilian Lichtner

## Aufgabe 1

_1)_
Sei eine Theorie $T$ Axiomatisierbar und vollständig.
Dann können wir alle Formeln in $T$ in endlicher Zeit aufzählen und kommen dann in endlicher Zeit an jeder Formel $\varphi$ oder ihrer Negation $\neg \varphi$ vorbei, um zu entscheiden ob eine beliebige Formel $\varphi$ in unserer Theorie $T$, listen wir also einfach systematisch alle Sätze auf, kommen wir an $\varphi$ vorbei geben wir $\varphi \in T$ zurück kommen wir an $\neg \varphi$ vorbei geben wir $\varphi\not\in T$ zurück.

_2)_

Seien $T_1$ und $T_2$ zwei Theorien mit dem selben Vokabular, sodass:

1. $T_1 \subseteq T_2$ 
2. $T_1$ ist vollständig
3. $T_2$ ist erfüllbar.

Da $T_1$ vollständig ist und $T_1 \subseteq T_2$ enthält es mindestens alle wahren Aussagen über dem Vokabular. Da $T_2$ erfüllbar ist, existiert mindestens ein Modell für $T_2$ das alle Aussagen in $T_2$ wahr macht. 
Weil jede wahre Aussage in $T_1$ auch in $T_2$ ist, folgt dass alle Modelle von $T_2$ auch Modelle von $T_1$ sind. Daher gilt das $T_1$ ebenfalls erfüllbar ist.

Wir wissen nun, dass $T_1$ erfüllbar ist und alle Modelle von $T_2$ auch Modelle von $T_1$ sind. Das impliziert, dass $T_2 \subseteq T_1$, laut Annahme gilt bereits $T_1 \subseteq T_2$ und daher gilt $T_1 = T_2$.


## Aufgabe 2

$$\begin{align}
&\forall x, x' \exists y_1, y_2, y_3 \left( x <x' \to \left(\left(\bigwedge^3_{i=1} x < y_i \land y_i < x'\right) \land \left(y_1 < y_2 < y_3 \right)\right)\right)\\
\iff&\forall x, x' \left( x <x' \to \exists y_1, y_2, y_3\left(\left(\bigwedge^3_{i=1} x < y_i \land y_i < x'\right) \land \left(y_1 < y_2 < y_3 \right)\right)\right)\\
\iff&\forall x, x' \left( x <x' \to \left(\left( x < x'\right) \land \exists y_1, y_2, y_3\left(y_1 < y_2 < y_3 \right)\right)\right)\\
\iff&\forall x, x' \left( x <x' \to \left(\left( x < x'\right) \land \top\right)\right)\\
\iff&\forall x, x' \left( x <x' \to \left(x < x'\right)\right)\\
\iff&\forall x, x' \left(\top\right)\\
\iff&\top
\end{align}$$


## Aufgabe 3

$$\begin{align}
&\forall x, x' \exists y_1, y_2, y_3 \left( x <x' \to \left(\left(\bigwedge^3_{i=1} x < y_i \land y_i < x'\right) \land \left(y_1 < y_2 < y_3 \right)\right)\right)\\
\iff&\forall x, x' \left( x <x' \to \exists y_1, y_2, y_3\left(\left(\bigwedge^3_{i=1} x < y_i \land y_i < x'\right) \land \left(y_1 < y_2 < y_3 \right)\right)\right)\\
\iff&\forall x, x' \left( x <x' \to \left(\left(s^3(x) < x'\right) \land \exists y_1, y_2, y_3\left(y_1 < y_2 < y_3 \right)\right)\right)\\
\iff&\forall x, x' \left( x <x' \to \left(\left(s^3(x) < x'\right) \land \top\right)\right)\\
\iff&\forall x, x' \left( x <x' \to s^3(x) < x'\right)\\
\iff&\exists x, x' \left( x <x' \land \neg \left(s^3(x) < x'\right)\right)\\
\iff&\exists x, x' \left( x <x' \land \left(s^3(x) = x' \lor x' < s^3(x)\right)\right)\\
\iff&\exists x, x' \left( x < x' \land s^3(x) = x'\right) \lor \exists x,x' \left(x < x' \land x' < s^3(x)\right)\\
\iff&\exists x \left( x < s^3(x) \right) \lor \exists x,x' \left(x < x' \land x' < s^3(x)\right)\\
\iff& \top \lor\exists x,x' \left(x < x' \land x' < s^3(x)\right)\\
\iff&\top
\end{align}$$
