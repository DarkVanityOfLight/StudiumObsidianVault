
fuer bis zu 4 Variablen ist die Berechnung von Primimplikanten einfach da:

- Adjazente Cubes sind direkte Nachbarn und Teilen sich eine Kante. 
- Cubes vom Grad $k$ sind Rechtecke der groesse $2^k$

bei mehr als vier Variable sind Adjazente Cubes immer noch Symmetrisch zur Spiegelachse und ein Cube vom Grad $k$ ist die Vereinigung von Rechtecken mit der groesse $2^k$  die symmetrisch zu einer der Achsen im KV-Diagram sind

Wir minimieren jetzt indem wir alle Implikanten mit der Minimalen anzahl von Primimplikanten überdecken.
Implikanten sind Rechtecke die $2^k$ Felder abdecken die eine $1$ sind und symmetrisch zu den Achsen sind.

Primimplikanten sind dann Maximale Rechtecke die aus Feldern mit $1$ bestehen.
Wegen Quine wählen wir die Primimplikanten so das sie sich nicht überdecken.

![kv1](kv1.png)

$$\neg d \lor a\land b \land \neg c$$
