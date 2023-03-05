Jede Zahl $n\in \mathbb Z\setminus\lbrace 0, -1, 1\rbrace$ hat eine eindeutige Darstellung
$$n = \pm p_{1}^{r_{1}} \cdot ...\cdot p_{s}^{r_{s}}$$
mit [Primzahlen](Primzahl.md) $p_{1} < ..., < p_{s}$ und $r_{i}\in\mathbb N$. Die $p_{i}$ heißen Primfaktoren von $n$

---

## Beweis
### Existenz: 

Existenz der [Primfaktorzerlegung](Primfaktorzerlegung.md) mit Induktion nach $n$:
$n = 2$ ist eine Primzahl. Ist $n > 2$ und keine Primzahl, dann ist $n = a\cdot b$ mit $a, b \not=1$. Da $a,b < n$, haben $a$ und $b$ nach Induktionsvoraussetzung Zerlegungen, und durch sortieren der Primfaktoren erhalten wir eine Primfaktorzerlegung von $n = a\cdot b$.

### Eindeutigkeit

$n=2$ ist klar. Sei $n > 2$ und
$$n = p_{1} \cdot ... \cdot p_{s} = q_{1} \cdot ... \cdot q_{t}$$ mit $p_{1} \le ... \le p_{s}$ und $q_{1}\le ... \le q_{t}$. Ist $s=1$ oder $t=1$ dann, ist $n$ prim, und die Behauptung ist klar. Seien also $s, t \ge 2$.
Ist $p_{1} = q_{1}$ dann hat
$$p_{2} \cdot ... \cdot p_{s} = q_{2} \cdot ... \cdot q_{t} <  n$$
nach Induktionsvoraussetzung eine eindeutige Primfaktorzerlegung und die Behauptung folgt.
Angenommen es waere $p_{1} < q_{1}$. Dann gilt

$$n > \underbrace{p_{1} \cdot (p_{2}\cdot ... \cdot p_{s} = q_{2} \cdot ... \cdot q_{t})}_{=: N_{1}} = \underbrace{(q_{1} - p_{1}) \cdot q_{2} \cdot ... \cdot q_{t}}_{=: N_{2}} \ge 2$$
also hat $N_{1} = N_{2}$ nach Induktionsvoraussetzung eine eindeutige Primfaktorzerlegung.