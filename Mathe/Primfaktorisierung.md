
## Probedivision
$n \in \mathbb N$ zusammengesetzt
Für den kleinsten Primteiler $P$ von $n$ gilt:
$P \leq m := \lfloor\sqrt n\rfloor$
Teste $P|n$ Ziehe $p$ raus falls teilbar

### Beweis
$n = p \cdot q \implies p^2 \leq p \cdot q = n$
$p\leq q$

### Beispiel
Fakt. $234$
$p \leq \lfloor \sqrt 234\rfloor = 15$
Teste ab 234 durch $p$ prim $p \leq 15$ teilbar
$234 = 2 \cdot 117 \qquad p\leq \lfloor\sqrt{117}\rfloor = 10$
$39 = 3\cdot 13 \qquad p\leq \lfloor p \leq \sqrt{39} \rfloor = 6$

$p \leq \lfloor \sqrt{13}\rfloor = 3$

