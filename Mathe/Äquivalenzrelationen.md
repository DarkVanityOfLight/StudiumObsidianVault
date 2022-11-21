Sei $M$ Menge und $R\subset M\times M$ [Reflexiv](Halbordnung.md#Reflexiv) und [Transitiv](Halbordnung.md#Transitiv).
Ist $R$ außerdem symmetrisch dh. $(m, n) \in R \implies (n, m)\in R$
so heißt $R$ Äquivalenzrelation.

Schreibe $m \sim n$ für $m, n \in R$ dann bedeutet
- reflexiv, dass $m \sim m \qquad \forall m\in M$ 
- transitiv, dass $m\sim l, l\sim n \implies  m\sim n \quad \forall m,n \in M$
- symmetrisch, dass $m \sim n \implies n\sim m\quad \forall m, n \in M$

$f: M\to N$ $m_1 \sim m_2 :\iff f(m_1) = f(m_2)$

$M$ Menge $\sim$ Äquival. rel. $m\in M$
$[m] = \left\{n\in M : n \sim m\right\} \subset 2^M$

## Kanonische Abbildung

Wir schreiben $M/\sim = \{[m]|m\in M\} \subset 2^M$ für die Menge der Äquivalenzklassen von $\sim$ und

$$\begin{align}
\pi :& M \to M/\sim\\
&m \mapsto [m]\\
&\text{surjektiv}
\end{align}$$
für die kanonische Abbildung von $\sim$.
#prüfungszettel 

### Beweis
$$\begin{align}
&[m] \cap [n] \not = \phi\\
&\implies\exists a \in [m] \cap [n] \implies a \sim m \land a \sim n\\
&\underbrace{\implies}_{sym} m \sim a \land a \sim n\\
&\underbrace{\implies}_{trans} m\sim n
\end{align}$$

Zeige $[m] = [n]$. Sei $a \in [m] \implies m\sim a \implies n\sim a\implies a\in[n]$
Also $[m] \subset [n]$ und $[n]\supset[m]$

$m_1 \sim m_1 \iff [m_1] = [m_2]$


## Beispiel
Gleich groß sein ist Äquivalenzrelation.
Gleich groß bis auf 1 cm Unterschied ist nicht transitiv
$f: M \to N$ $m_1 \sim m_2: \iff f(m_1) = f(m_2)$

## Äquivalenzklasse
$M$ Menge , $\sim$ auf $M$
$[m] = \{n\in M| m \sim n\} \subset M$
heißt Äquivalenzklasse von $m$
$m$ heißt Repräsentant von $[m]$

## Repräsentantensystem

$\{m_1, ..., m_r\}$ vollständiges Repräsentantensystem

$$M = \bigcup^r_{i=1} [m_i]$$

---

> Je zwei Äquivalenzklassen sind gleich oder disjunkt

### Beweis
Sei $[m] \cap [n] \not = \emptyset$. Wir müssen $[m] = [n]$ zeigen. Ist $a\in [m] \cap [n]$, also $a\sim m$ und $a\sim n$, dann folgt mit Symmetrie und Transitivität, dass $m\sim n$, also $m \in [n]$. Sei nun $a \in [m]$ beliebig. Dann gilt $a\sim m$ und $m \sim n$, also $a \sim n$,. das heißt $a\in [n]$. Wir haben also $[m] \subset [n]$ gezeigt. Die andere Inklusion folgt genauso. $\blacksquare$
Insbesondere gilt;
$$m \sim n \iff [m] = [n]$$
d.h Äquivalenz von Elementen von $M$ übersetzt sich in Gleichheit von Elementen von $M/\sim$.

## Partitioniert
Der Satz zeigt auch: Eine Äquivalenzrelation partitioniert die Menge $M$ in die Äquivalenzklassen. Partitionieren bedeutet hier, eine Menge als [disjunkte](Disjunkt.md) Vereinigung von nicht leeren Mengen zu schreiben