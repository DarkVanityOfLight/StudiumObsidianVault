Sei $M$ Menge und $R\subset M\times M$ [Reflexiv](Halbordnung.md#Reflexiv) und [Transitiv](Halbordnung.md#Transitiv).
Ist $R$ außerdem symmetrisch dh. $(m, n) \in R \implies (n, m)\in R$
so heißt $R$ Äquivalenzrelation.

Schreibe $m \sim n$ für $m, n \in R$ dann $m \sim m \qquad \forall m\in M$ $m\sim l, l\sim n \implies  m\sim n$
>$m \sim n \implies n\sim m$

$f: M\to N$ $m_1 \sim m_2 :\iff f(m_1) = f(m_2)$

$M$ Menge $\sim$ Äquival. rel. $m\in M$
$[m] = \left\{n\in M : n \sim m\right\} \subset 2^M$

## Kanonische Abbildung

$M/\sim = \{[m]|m\in M\} \subset 2^M$

$$\begin{align}
\pi :& M \to M/\sim\\
&m \mapsto [m]\\
&\text{surjektiv}
\end{align}$$
#prüfungszettel 

Je zwei Äquivalenz klassen sind gleich oder disjunkt.
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

$\{m_1, ..., m_r\}$ vollständiges Repräsentatensystem

$$M = \bigcup^r_{i=1} [m_i]$$

