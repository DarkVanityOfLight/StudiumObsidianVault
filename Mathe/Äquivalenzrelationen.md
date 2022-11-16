Sei $M$ Menge und $R\subset M\times M$ [Reflexiv](Halbordnung.md#Reflexiv) und [Transitiv](Halbordnung.md#Transitiv).
Ist $R$ außerdem symmetrisch dh. $(m, n) \in R \implies (n, m)\in R$
so heißt $R$ Äquivalenzrelation.

Schreibe $m \sim n$ für $m, n \in R$ dann $m \sim m \qquad \forall m\in M$ $m\sim l, l\sim n \implies  m\sim n$
>$m \sim n \implies n\sim m$

$f: M\to N$ $m_1 \sim m_2 :\iff f(m_1) = f(m_2)$

$M$ Menge $\sim$ Äquival. rel. $m\in M$
$[m] = \left\{n\in M : n \sim m\right\} \subset 2^M$

## Kanonische Abbildung

$$\begin{align}
\pi :& M \to M/\sim\\
&m \mapsto [m]
\end{align}$$
#prüfungszettel 

Je zwei Äquivalenz klassen sind gleich oder disjunkt.
### Beweis
$$\begin{align}
&[m] \cap [n] \not = \phi\\
&\text{exist} a \in [m] \cap [n] \implies a \sim m \text{und} a \sim n\\
&\implies m \sim a \text{und} a \sim n
\end{align}$$

## Beispiel
Eigenschaft von zwei Menschen gleich groß zu sein ist eine Äquivalenz rel
(gleich groß bis auf 1 cm)

