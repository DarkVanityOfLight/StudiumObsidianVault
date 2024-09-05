
Sei $\Sigma$ ein [Alphabet](Alphabet.md). Eine (formale) Sprache $L$ über dem [Alphabet](Alphabet.md) $\Sigma$ ist eine beliebige [Teilmenge](Teilmengen.md) von $\Sigma^*$, d.h. $L\subseteq\Sigma^*$.


Wir definieren die [Konkatenation](Wort.md#Konkatenation) von Sprachen $K, L \subseteq \Sigma^*$ als:
$$KL = \lbrace uv | u\in K, v\in L\rbrace$$

---

$L^n$ ist induktiv definiert durch $L^0 = \lbrace \varepsilon\rbrace$ und $L^{n+1} = LL^n$ für alle $n\in\mathbb N$.

---

$$L^* = \bigcup_{n\in\mathbb N} L^n$$

---

$$L^+ = \bigcup_{n\ge 1} L^n$$

---

Wenn $L$ eine Sprache ist und $w\in L^*$ dann kann man $w$ schreiben als $w = w_1 \dots w_n$, wobei $w_1,\dots,w_n \in L$

Diese Darstellung ist jedoch nicht eindeutig!


## Regulär

Eine Sprache $L \subseteq \Sigma^*$ heißt regulär, wenn sie von einem DFA erkannt wird, d.h. es existiert ein [Deterministischer endlicher Automat](Deterministische%20endliche%20Automaten.md) $A$ mit $L(A) =  L$.
