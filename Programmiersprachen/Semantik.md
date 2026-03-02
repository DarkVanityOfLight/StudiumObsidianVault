Die Semantik legt die Bedeutung von Programmen fest, die Bedeutung eines arithmetischen Ausdrucks ist eine Zahl. Die Semantik lässt sich mit Auswertungsregeln beschreiben: 
- Wenn $a11$ zu $1$ auswertet, dann wertet $a11 + 815$ zu $816$ aus;
- Wenn $a11 + 815$ zu $816$, dann wertet $4711 * (a11 + 815)$ zu $3844176$ aus.
Die Auswertungsregeln orientieren sich eng an der Struktur eines Programms die Bedeutung eines Ausdrucks wird auf die Bedeutung der Teilausdrücke zurückgeführt(kompositional).

## Statische Semantik
Agiert als "Filter" ob ein Programm ausführbar ist oder nicht. Denn nicht alle Ausdrücke ergeben Sinn. Um sicherzustellen das die einzelnen Ausdrücke Sinn ergeben gibt es Typen

$i \in Type ::=...$

$\over false: Bool$ $\over true: Bool$

$e_1 : \text{Bool} \qquad e_2: t \qquad e_3: t \over \text{if}\, e_1\,\text{then}\,e_2\,\text{else}\, e_3:t$





$e_1: Nat\qquad e_2: Nat \over e_1 < e_2: Bool$


### Beispiel
49 + true(nicht Valide)

## Dynamische Semantik
$v \in Val ::= ...$
Die Dynamische Semantik ist die eigentliche Auswertung+
$$\begin{align}
v ::&= ...\\
&| false\\
&| true
\end{align}$$

$\over false\Downarrow false$ $\over true \Downarrow true$

$e_1\Downarrow true \qquad e_2 \Downarrow v\over if\,e_1\,then\,e_2\,else\, e_3\Downarrow v$ $e_1\Downarrow false\qquad e_3 \Downarrow v\over if\,e_1\,then\,e_2\,else\, e_3\Downarrow v$

#### Beispielrechnung
$$
 {
 {{4711 \Downarrow 4711} \qquad {815 \Downarrow 815}
 \over 4711 < 815 \Downarrow false}
 \over
 if 4711 < 815\, then\, false\, else\, true \Downarrow true} \qquad {\over true \Downarrow true} \qquad {\over \text{"yes"} \Downarrow \text{"yes"}}
 \over
 {if\, (if\, 4711 < 815\, then\, false\, else\, true)\, then \text{"yes"}\, else \text{"no"} \Downarrow \text{"yes"}}
$$



