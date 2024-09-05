In der Praxis hat man oft [Bedingte Wahrscheinlichkeiten](Bedingte%20Wahrscheinlichkeiten.md) $P(F|E)$ gegeben und möchte daraus die sogenannte inverse bedingte Wahrscheinlichkeit $P(E|F)$ berechnen.

Sei $\Omega$ ein diskreter Wahrscheinlichkeitsraum und sei
$$\Omega = A_1 \cup \dots \cup A_r$$
eine [Partition](Partition.md) von $\Omega$ in [Ereignisse](Ereignisse.md) (die $A_i$ sind paarweise disjunkt) und sei $B$ ein weiteres Ereignis. Dann gilt
$$P(A_i | B) = \frac{P(A_i) \cdot P(B | A_i)}{P(A_1) \cdot P(B | A_1) + \dots + P(A_r) \cdot P(B| A_r)}$$

Wir können uns den Satz so vorstellen:
Das Ereignis $B$ liefert eine Evidenz, dass $A_i$ vorliegt. Wir wissen mit welcher Wahrscheinlichkeit $A_i$ eintritt. Weiter wissen wir, mit welcher Wahrscheinlichkeit $P(B | A_i)$ das Ereignis $B$ eintritt unter der Voraussetzung, dass $A_i$ vorliegt. Dann können wir die Wahrscheinlichkeit $P(A_i | B)$ von $A_i$ bestimmen unter der Voraussetzung, dass $B$ eintritt.

