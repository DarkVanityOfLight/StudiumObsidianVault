Seien $a, b \in \mathbb Z, b \not = 0$ Dann gibt es eindeutig bestimmte Zahlen $q, r \in \mathbb Z$ mit $a = b \cdot q + r$ und $0 \leq r < |b|$

## Beispiel
$a = 1000, b=3$
$1000 = 3 \cdot 333 + 1$

## Beweis der Existenz
$0\exists b> 0$
$\{w\in \mathbb Z | b\cdot w > a\} \not = \emptyset$
hat  kleinstes Element w. $q:= w-1$ $r:= a-q\cdot b$

### Zu Zeigen
$r<b$

$b\cdot(q+1) = b\cdot w > a$
$r=a-qb < (q+1) \cdot b - qb = b$
#prüfungszettel 

$b\cdot q \leq a$
$r = a - b\cdot q \geq 0$

## Beweis der Eindeutigkeit
Sind $b \cdot q_1 + r_1 = a = b \cdot q_2 + r_2$
$0\exists\quad r_2\leq r_1\quad 0\leq r_1 -r_2 = b\cdot\underbrace{(q_2 -q_1)}_{0} < |b|$
$\implies q_1 = q_2 \implies r_1 = r_2$


