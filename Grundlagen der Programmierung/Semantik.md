Die Semantik legt die Bedeutung von Programmen fest, die Bedeutung eines arithmetischen Ausdrucks ist eine Zahl. Die Semantik lässt sich mit Auswertungsregeln beschreiben: 
- Wenn $a11$ zu $1$ auswertet, dann wertet $a11 + 815$ zu $816$ aus;
- Wenn $a11 + 815$ zu $816$, dann wertet $4711 * (a11 + 815)$ zu $3844176$ aus.
Die Auswertungsregeln orientieren sich eng an der Struktur eines Programms die Bedeutung eines Ausdrucks wird auf die Bedeutung der Teilausdrücke zurückgeführt(kompositional).

## Statische Semantik
Agiert als "Filter" ob ein Programm ausführbar ist oder nicht. Um dies sicherzustellen gibt es Typen.

$\over false: Bool$ $\over true: Bool$

$e_1 : Bool\ e_2:t\ e_3: t \over if\ e_1\ then\ e_2\ else\  e_3:t$

$e_1: Nat\ e_2: Nat \over e_1 < e_2: Bool$


### Beispiel
49 + true(nicht Valide)

## Dynamische Semantik
Die Dynamische Semantik ist die eigentliche Auswertung+
$$\begin{align}
v ::&= ...\\
&| false\\
&| true
\end{align}$$

$\over false\Downarrow false$ $\over true \Downarrow true$

$e_1\Downarrow true\ e_2 \Downarrow v\over if\ e_1\ then\ e_2\ else\  e_3\Downarrow v$ $e_1\Downarrow false\ e_3 \Downarrow v\over if\ e_1\ then\ e_2\ else\  e_3\Downarrow v$

