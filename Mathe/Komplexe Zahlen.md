# Komplexe Zahlen

Die Menge $C$ der Komplexen Zahlen ist definiert als die Menge der geordneten Paare [reeller Zahlen](Reelle%20Zahlen.md) $\{(x_1, x_2)| x_1 \in R, x_2 \in R\} = R \times R = R^2$ mit den folgenden Verknüpfungen für $(x_1, x_2)$ und $(y_1, y_2)\in C$:

## Addition
$$(x_1, x_2) + (y_1, y_2) = (x_1 + y_1, x_2+ y_2)$$
## Multiplikation
$$(x_1, x_2) \cdot (y_1, y_2) = (x_1y_2 -x_2y_2, x_1y_2+x_2y_1)$$
Es gelten das [Kommutativgesetz](Kommutativgesetz.md), [Assoziativgesetz](Assoziativgesetz.md) und [Distributivgesetz](Distributivgesetz.md)

## Die imaginäre Einheit 
Die komplexe Zahl $(0, 1)$ hat die Eigenschaft:
$$(0, 1) \cdot (0, 1) = (0\cdot 0 - 1 \cdot 1, 0 \cdot 1  + 1 \cdot 0 = -1)$$
Wir setze $i := (0,1)$ und nennen $i$ imaginäre Einheit
Dann gilt also $i^2 = -1$

## Realteil, Imaginärteil, Konjugierte
Ist z $z = x_1 + ix_2 \in C$, so definieren wir 
- Realteil von z: $Re(z) := x_1$
- Imaginärteil von z: $Im(z) := x_2$
- Konjugiert komplexe Zahl zu z: $\bar z := x_1 -ix_2 = (x_1, -x_2)$
### Rechenregeln für die Konjugation
Seien $x_1 +ix_2$ und $w \in C$. Dann gilt:
a) $\bar z = z$
b) $z\bar z = x_1^2 + x_2^2$
c) $\overline{z+w} = \bar{z} + \bar w$
d) ${\bar 1 \over z} = {1 \over \bar z}$
e) $\overline{z \cdot w}$
f) $z = \bar z \iff z \in R$
g) $Re(z) = {1\over 2}(z + \bar z)$
h) $Im(z) = {1\over 2i}(z-\bar z)$

## Betrag einer komplexen Zahl
Für $z = x_1 +ix_2 \in C$ heißt $|z| := \sqrt{x_1^2+x_2^2}$ der Betrag von z.
![Betrag-komplexe-Zahl-Beispiel-polar-1024x709](Betrag-komplexe-Zahl-Beispiel-polar-1024x709.png)

### Rechenregeln des Betrags
a) $|z \cdot w| = |z|\cdot |w|$
b) $|{z\over w}| = |{z\over w}|\ für\ w \not = 0$
c) $|\bar z| = z$
d) $|w-z| = |z -w|$
e) $-|z| \leq Re(z) \leq |z|$
f) $-|z| \leq Im(z) \leq |z|$
g)$|z+w| \leq |z| + |w|$ Dreiecksgleichung


