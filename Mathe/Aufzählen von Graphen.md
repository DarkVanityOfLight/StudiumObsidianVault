Ein Graph (ungerichtet und ohne Merhfachkanten) ist ein Tupel $(V, E)$ aus einer [Menge](Mengen.md) $V$ und einer [Teilmenge](Teilmengen.md) $E \subset \left({V\atop 2}\right)$. Dabei bezeichnet $\left({V\atop 2}\right)$ die Menge der zweielementigen Teilmengen von $V$, und $V$ heisst [Menge](Mengen.md) der Vertices(oder Knoten oder Ecken) und E Menge der Kanten(oder Edges) des Graphen.

Es gibt genau $2^{\left({n\atop 2}\right)}$ Graphen auf $n$ Vertices

### Beispiel
Durch $V = \{1, 2, 3\}$ und $E=\{{1, 2}, (2, 3)\}$ ist der Graph $\Gamma = (V, E)$ gegeben

```mermaid
graph TD

A((1)) --- B((2)) --- C((3))
```

## [Isomorphe](Isomorphismen.md) Graphen
Zwei Graphen $(V_{1}, E_{1})$ und $(V_{2}, E_{2})$ heißen [Isomorph](Isomorphismen.md), wenn eine [bijektive](Bijektiv.md) [Abbildung](Abbildungen.md) $\varphi: V_{1}\to V_{2}$ existiert sodass
$\{v, w\} \in E_{1}\iff \left\{\varphi(v), \varphi(w)\right\} \in E_2$
für alle $v, w\in V_1$

Isomorphie von Graphen ist eine [Äquivalenzrelationen](Äquivalenzrelationen.md). Die $S_n$ operiert auf der Menge aller Graphen durch Anwenden von $\sigma \in S_n$ auf Vertices der Kanten

> Es gibt genau 4 Isomorphie klassen von Graphen mit 3 Ecken

