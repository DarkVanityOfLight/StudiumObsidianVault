Wir erhalten eine Liste aller Primzahlen kleiner gleich $N \in\mathbb N, N \ge 4$ wie folgt:

1. Erstelle eine boolesche Liste $L$ mit einem Eintrag zu jeder Zahl $2, ..., N$. Markiere alle Zahlen als prim (true). Setze $p=2$
2. Markiere alle $j\cdot p$ mit $j \ge p$ als nicht prim (false).
3. Finde das kleinste $q > p$, das als prim (true) markiert ist. Falls $q > \sqrt{n}$ gebe $L$ zurück. Setze $p := q$, gehe zu Schritt (2).

## Beweis
In Schritt(2) sind alle $j\cdot p$ mit $2\leq j< p$ schon aus vorherigen Schritten als $false$ markiert, da sie einen Primteiler $< p$ besitzen. Somit sind alle echten Vielfachen von $p$ als $false$ markiert.
Die Zahl $q$ in Schritt (3) ist stets prim: Nach Wahl von $q$ ist $p$ die grösste Primzahl $< q$, aus vorherigen Schritten sind alle Vielfachen $j\cdot x$ von allen Primzahlen $x \leq p$ als $false$ markiert. Wäre $q$ nicht prim, müsste $q$ aber ein solches $p$ als Primteiler haben, wäre also als $false$ markiert.
Sobald der Algorithmus terminiert, sind also alle Zahlen als $false$ markiert, die eine Primzahl $p \leq \sqrt{N}$ als echten Teiler haben, d.h nicht prim sind.

