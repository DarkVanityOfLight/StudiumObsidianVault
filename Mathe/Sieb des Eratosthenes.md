Liste aller Primzahlen $\leq N$ $N \geq 4$

- Erstelle [boolsche](Warheitswerte(Boolean).md) Liste zu $2,..., N$ Markiere alle als true
- Markiere alle $j\cdot p, j \geq p$ als nicht prim (false)
- Finde kleinste $q>p$ das als prim(true) markiert ist
- Falls das $q > \sqrt q$ return L
- Sonst  $p=q$
- GoTo 2