Sei K ein [Angeordneter Koerper](Angeordneter%20Koerper.md). Die [Folge](Folgen.md) $(a_n)$ in $K$ heißt Konvergent gegen den Grenzwert $a\in K$, wenn es zu jedem $\epsilon \in K$, $e > 0$ ein $N \in \mathbb N$ gibt mit
$|a_n -a| < \epsilon$ für alle $n\leq N$

Ist $(a_n)$ konvergent gegen ein $a\in K$ so heißt $(a_n)$ konvergent, sonst [[Divergent]]


## Als Spiel
1) Spieler A gibt ein $\epsilon > 0$ vor
2) Spieler B muss $N$ finden sodass der Abstand von $a_N$ und $a$ kleiner als $\epsilon$ ist und auch alle weiteren Folgeglieder in diesem Abstand bleiben
$(a_n)$ ist konvergent gegen $a$ wenn B immer gewinnt

---

Der Grenzwert a einer konvergenten Folge ist eindeutig.
Schreibe $\lim_{n \to \infty} a_n := a$

### Beweis
Angenommen $a\not = b$ sind Grenzwerte von $(a_n)$
$\implies |a-b| \not = 0$

$\epsilon := {1\over 3}\cdot |a-b| > 0$

Zu $\epsilon := {1\over3} \cdot |a-b|$
$\exists N_1: |a_n -a| < \epsilon\qquad \forall n\geq N_1$
$\exists N_2: |a_n - b|< \epsilon \qquad \forall n\geq N_2$
Fuer $n \geq \max\{N_1, N_2\}$

$|a-b| = |a-a_n + a_n -b| \leq |a_n -a| + |a_n -b|$
$< 2\cdot \epsilon = {2\over 3} |a-b|$
$\implies a = b$


## Rechenregeln
$(a_n)$ kons
$(b_n)$ kons
$\implies$ $(a_n + b_n)$ kons
$(a_n \cdot b_n)$ kons

$a_1+b_1, a_2 +$
