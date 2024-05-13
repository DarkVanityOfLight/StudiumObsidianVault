---
tags:
---

Ein Wort über dem [Alphabet](Alphabet.md) $\Sigma$ ist eine endliche Zeichenkette der Form $a_1a_2\dots a_n$ mit $a_i \in\Sigma$ für $1 \le i \le n$.

Die [Menge](Mengen.md) aller Wörter über dem [Alphabet](Alphabet.md) $\Sigma$ wird mit $\Sigma^*$ bezeichnet.



## Leeres Wort
Das leere Wort ist das Wort der Länge $0$, welches mit $\epsilon$ bezeichnet wird.

---

Die [Menge](Mengen.md) aller nicht leeren Wörter ist $\Sigma^+ = \Sigma^{*} \setminus\lbrace\varepsilon\rbrace$

---
## Länge
Die Länge eines Wortes $w = a_1 \dots a_n$ ist $n$. Wir schreiben auch $|w| = n$.

## Konkatenation

Seien $u = a_1\dots a_m$ und $v = b_1\dots b_n$ zwei Wörter. Das Wort

$$u\cdot v = a_1\dots a_m b_1\dots b_n$$
ist die Konkatenation der Wörter $u$ und $v$.
Anstatt $u \cdot v$ schreiben wir meistens nur $uv$.

Die Konkatenation ist ein binäre Operation:
$$\Sigma^* \times \Sigma^* \to \Sigma^*$$

Offensichtlich gilt für alle Wörter $u, v, w \in \Sigma^*$
- $(u \cdot v) \cdot w = u \cdot (v\cdot w)$
- $\varepsilon \cdot u = u = u\cdot \varepsilon$


## Algebraische Struktur

Die Struktur $(\Sigma^*, \cdot, \varepsilon)$ ist ein [Monoid](Gruppe.md#Monoid), nämlich das von $\Sigma$ erzeugte freie Monoid. Dieser Monoid ist nicht kommutativ d.h. $ab \not = ba$ für $a, b \in \Sigma$ mit $a\not = b$.
$(\Sigma^*, \cdot, \varepsilon)$ ist keine [Gruppe](Gruppe.md), denn für $a\in\Sigma$ gibt es kein $a^{-1} \in\Sigma^*$ mit $a \cdot a^{-1} = \varepsilon$.


## Anzahl an Wörtern

Angenommen $\Sigma$ ist ein [Alphabet](Alphabet.md) mit $s$ Symbolen: $|\Sigma| = s$

Es gibt genau $s^n$ viele Woerter der Laenge $n$ ueber dem Alphabet $\Sigma$

$$|\lbrace w\in\Sigma^* : |w| = n \rbrace| = s^n$$

