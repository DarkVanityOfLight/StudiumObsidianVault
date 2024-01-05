Eine Signatur $\sigma$ ist eine(endliche/unendliche) Menge, die aus zwei Objektsorten besteht:
1. Funktionssymbole: $f, h, g, \dots$
2. Relationssymbole(auch Prädikatssymbole genannt): $R_1, R_2, \dots$

Eine Signatur ordnet jedem Funktions- und Relationssymbol eine natürliche Zahl, die __Stelligkeit__ (auch __Arität__) genannt wird. Wenn $r$ die Stelligkeit der [Funktion](Mathe/Funktionen.md) $f$ ist, schreiben wir in der Signatur $f/r$ statt $f$, damit die Arität der [Funktion](Mathe/Funktionen.md) deutlich ist. Gleichermaßen schreiben wir in der Signatur $R/r$ statt $R$ für jede $r$-stellige Relation $R$. Ein spezieller Fall wird für $0$-stelliges Funktionssymbol $f$ reserviert, in welchem Fall $f$ auch ein __Konstantensymbol__ genannt wird. Mit Symbolen $a, b, c$ bezeichnen wir meistens Konstantensymbole. Als Beispiel definieren wir die Signatur $\sigma_{\mathbb N}$, die aus Folgendem besteht: Konstantensymbole $0, 1$ und die binären Funktionssymbole $+$ und $\times$:
$$\sigma_{\mathbb N} := \lbrace 0, 1, <_{/2},  +_{/2}, \times_{/2}$$

Signaturen ohne Funktionssymbole werden als __relationale__ Signatur bezeichnet. Solche Signaturen spielen eine ausschlaggebende Rolle in der Informatik. Wir haben zum Ziel, die Menge $FO(\sigma)$ der prädikatenlogischen Formeln mit der Signatur $\sigma$ zu definieren. Zu diesem Zweck kommt als erstes eine rekursive Definition der __Terme__.
