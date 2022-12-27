
## Probedivision
Sei $n \in \mathbb N$ zusammengesetzt(nicht Prim). Fuer den kleinsten Primteiler $p$ von $n$ gilt:
$$P \leq m := \lfloor\sqrt n\rfloor$$

Kennen wir alle Primzahlen $p \leq m$, dann testen wir $p | n$ mit [Division mit Rest](Division%20mit%20Rest.md). Damit können wir eine gegebene Zahl $n$ faktorisieren.


### Beweis
Schreibe $n = p \cdot q$ Dann gilt  $p^2 \leq p \cdot q = n$ also $p \leq \sqrt n$.
Wegen $p\in\mathbb N$ ist also $p\leq \lfloor \sqrt{n}\rfloor$.

### Beispiel
Zum Faktorisieren von $234$ mittels Probedivision testen wir zunächst, ob $n$ durch eine Primzahl $p \leq \lfloor \sqrt{234}\rfloor = 15$ teilbar ist. Wir finden $$
234 = 2 \cdot 117
$$
Ist $117$ nicht prim, so muss ein Primteiler $p\leq \lfloor\sqrt{117}\rfloor = 10$ vorkommen, wir finden $$117 = 3 \cdot 39$$
Ist $39$ nicht prim, so muss ein Primteiler $p \leq \lfloor \sqrt{39} \rfloor = 6$ vorkommen, und wir finden $$39 = 3\cdot 13$$
Schließlich ist $13$ prim, denn 13 ist durch keine Primzahl $p \leq \lfloor \sqrt{13} \rfloor =3$teilbar.
Die Probedivision erlaubt uns auch, alle Primzahlen $\leq n$ induktiv aufzuzählen, denn kennen wir schon alle Primzahlen $p\leq \lfloor \sqrt{n} \rfloor < n$, so können wir durch Faktorisieren entscheiden, ob $n$ prim ist.
