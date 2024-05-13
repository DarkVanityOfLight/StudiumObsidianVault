
Ein nichtdeterministischer endlicher Automat $A$ ist ein $5$-[Tupel](Tupel.md) $A = (Q, \Sigma, \Delta, I, F)$ wobei:
- $Q$ eine endliche [Menge](Mengen.md) an Zustaenden ist,
- $\Sigma$ ein endliches Eingabe[alphabet](Alphabet.md) ist
- $\Delta \subseteq Q \times \Sigma \times Q$ die Transitionsrelation ist
- $I\subseteq Q$ die Menge der Startzustände ist und
- $F\subset Q$ die Menge der Endzustände ist.


## Lauf

Sei $A = (Q, \Sigma, \Delta, I, F)$ ein NFA und $w = a_1\dots a_n \in \Sigma^*$ ein Wort.
Ein Lauf von $A$ auf $w$ ist eine [Folge](Mathe/Folgen.md) 
$$(q_0, a_1, q_1, a_2, q_2,\dots, q_{n-1}, a_n, q_n)$$
wobei $q_0, \dots, q_n\in Q, q_0 \in I$ und $(q_{i-1}, a_i, q_i) \in\Delta$ für alle $1\le i\le n$.
Der Lauf ist akzeptierend, wenn $q_n \in F$

---

## Erkannte Sprache

Die von einem NFA $A = (Q, \Sigma, \Delta, I, F)$ erkannte [Sprache](Sprache.md) ist 
$$L(A) = \lbrace w \in\Sigma^* | \text{es existiert ein akzeptierender Lauf von $A$ auf $w$} \rbrace$$
Wir sagen, dass ein Wort $w\in\Sigma^*$ von $A$ akzeptiert wird wenn $w\in L(A)$


