> Eine Abbildung $f: M \to N$ ist eine [Relation](Relation.md) $R\subset \underbrace{M}_{\text{Quelle}} \times \underbrace{N}_{\text{Ziel}}$ sodass es für jedes $m\in M$ genau ein $f(m)\in N$ gibt mit $(m, f(m)) \in R$.

## Schreibweise 
$$\begin{align}
f:& M \to N\\
&m \mapsto f(m)
\end{align}$$

## Graph
Die Relationenmenge $R$ bezeichnet man auch als Graphen
$$
Graph(f) := R = \{(m, f(m)) | m\in M\}
$$
von $f$


## Bild
Für $A\subset M$ heißt  $f(A) = \{f(m) | m\in A\}$ Bild von A unter f
$$Bild(f) := f(M) \subset N$$
## Urbild
Für $B\subset N$ heißt $f^{-1}(B) := \{m\in M | f(m) \in B\}$ Urbild von B unter f.


## Schubfachprinzip
Sind $M, N$ endliche Mengen und ist $: M\to N$ eine [injektiv](Abbildungen.md#Injektiv) Abbildung dann gilt $|M| \leq |N|$.

![Surjektiv](Surjektiv.md)

![Injektiv](Injektiv.md)

![Bijektiv](Bijektiv.md)

## Beispiel
$M = \{1,2,3\}$ $N= \{1, 2\}$injektive
$\implies |M| > |N| \implies$ es gibt keine inj. Abbildung $M\to N$

### Beweis
$$\begin{align}
|N| = \sum_{n\in N} 1 \geq \sum_{n\in N} \underbrace{|f^{-1}(\{n\})|}_{0 \text{falls} m \not\in Bild(f)\atop 1 \text{falls} m \in Bild(f)} \doteq |M|
\end{align}$$

denn $f^{-1}(\{n\})$ hat genau 1 Element, wenn $n$ im Bild von $f$ liegt,
(da $f$ injektiv), und ist leer sonst. Die zweite Gleichheit gilt, da $M$ die disjunkte Vereinigung
$$
M = \bigcup_{n\in N} \underbrace{f^{-1}(\{n\})}_{levelsets}
$$
der Level sets $f^{-1}(\{n\})$ der Abbildung $f$ ist: Eine Abbildung ordnet jedem Element $m \in M$ genau einen Wert $n$ zu. Auf diese Idee werden wir in Zusammenhang mit Äquivalenzrelationen zurückkommen.

Ist $f: M\to N$ bij. dann gibt es eine eindeutig bestimmte Umkehrabbildung
$f^{-1}: N \to M, n \mapsto m$ falls $f(m) = n$.
Es gilt $$\begin{align}
&f^{-1}(f(m)) = m& \forall m \in M\\
&f(f^{-1}(n)) = n& \forall n \in N
\end{align}$$
$Graph(f^-1) = \{f^{-1}(n), m| m \in M\}$

## Identische Abbildung
Sei $M$ eine Menge. Die identische Abbildung auf $M$ ist
$$\begin{align}
id_M :& M\to M\\
& m \mapsto m
\end{align}$$

ist $f: M\to N$ eine [bijektive](#Bijektiv) Abbildung, so gilt
$$
f^{-1} \circ f = id_M \qquad f\circ f^{-1} = id_N
$$
