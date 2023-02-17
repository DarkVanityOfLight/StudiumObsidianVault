Sei K ein [Angeordneter Körper](Angeordneter%20Körper.md). Die [Folge](Mathe/Folgen.md) $(a_n)$ in $K$ heißt Konvergent gegen den Grenzwert $a\in K$, wenn es zu jedem $\epsilon \in K$, $e > 0$ ein $N \in \mathbb N$ gibt mit
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
---


## Abgeschnittene Folge
Gegeben ist eine Folge $(a_n)$ und $N \in \mathbb N$, dann schreiben wir $(a_n)_{n\geq N}$ für die abgeschnittene Folge $(a_N, a_{N+1}, a_{N+2}, ...)$.

Ist $(a_n)$ konvergent, dann auch $(a_n)_{n\geq N}$ für jedes N, und beide Folgen haben denselben Grenzwert.



$K = \mathbb Q \qquad a_n = {1\over n}$
$\lim_{n\to \infty} {1\over n} = 0$

$\epsilon = {p\over q} \in \mathbb Q \quad \epsilon > 0$
$|a_n -a| = {1\over n} < {p\over q} = \epsilon\qquad \forall n \geq N := q+1$

## Beispiel
$a_n = (-1)^n$ divergent
Angenommen $(a_n)$ kann dann $\exists N$, $a\in \mathbb Q$
$$\begin{align}
|a_n -a| < 1\\
2 = |a_{n+1} - a_n| = |a_{n+1} -a+a - a_n| \leq |a_{n+1} -a| + |a_n -a| < 1+1 =2
\end{align}$$

## Notation
Für $(a_n)\qquad N\in \mathbb N$
ist  $(a_n)_{n \geq N} = (a_N, a_{N+1}, ...)$ weil
$(a_n)$ konvergent $\implies (a_n)_{\geq N}$ konvergent zum selben Grenzwert

---


## Rechenregeln
Sei $K$ ein angeordneter Körper und $(a_n)$ und $(b_n)$ konvergente Folgen in $K$ mit $lim_{n\to\infty} b_n = b$. Dann konvergieren die Folgen $(a_n + b_n)$ und $(a_n \cdot b_n)$ und es gilt
$$\begin{align}
&\lim_{n \to\infty}(a_n + b_n) = a + b\\
&\lim_{n\to\infty}(a_n \cdot b_n) = a\cdot b
\end{align}$$
Ist außerdem $a\not = 0$, dann gibt es ein $N$ mit $a_n \not = 0$ für alle $n \geq N$, die Folge $({1\over a_n})_{n\geq N}$ konvergiert und es gilt 
$$\lim_{n\to\infty} {1\over a_n} = {1\over a}$$

## Nach oben Beschränkt
Eine Folge $(a_n)$ heißt nach oben beschränkt, wenn es ein $C\in K$ gibt mit $a_n \leq C$ für alle n. 

## Nach unten Beschränkt
Sie heißt nach unten beschränkt, wenn es ein $C\in K$ gibt mit $a_n \geq C$ für alle $n$. 

## Beschränkt
Eine Folge $(a_n)$ ist beschränkt genau dann, wenn es ein $C\in K$ gibt mit $|a_n| \leq C$ für alle n.

Jede Konvergente Folge ist beschränkt.

