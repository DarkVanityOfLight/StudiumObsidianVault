Wir erhalten eine Liste aller Primzahlen kleiner gleich $N \in \mathbb N$, $N \leq 4$ wie folgt:

1) Erstelle eine boolsche Liste $L$ mit einem Eintrag zu jeder Zahl $2,..., N$. Markiere alle Zahlen als prim (true). Setze $p=2$
2) Markiere alle $j\cdot p$ mit $j \geq p$ als nicht prim (false).
3) Finde das kleinste $q > p$, das als prim (true) markiert ist. Falls $q > \sqrt{N}$ gebe $L$ zurück. Setze $p := q$, gehe zu Schritt (2).