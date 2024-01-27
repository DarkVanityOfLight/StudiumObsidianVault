
Eine __Theorie__ ist eine [Satzmenge](Satz.md) mit einer bestimmten [Signatur](Logik%20und%20Semantik%20von%20Programiersprachen/Signatur.md). Gegeben sei $\mathcal A$ eine $\sigma$-[Struktur](Struktur.md). Definiere die __Theorie__ von $\mathcal A$:
$$Th(\mathcal A) := \lbrace \varphi : \mathcal A \vDash \varphi\rbrace$$

Sei $\mathcal S$ eine [Menge](Mengen.md) von $\sigma$-Strukturen. Definiere die __Theorie__ von $\mathcal S$:
$$Th(\mathcal S) := \bigcap_{\mathcal A \in\mathcal S} Th(\mathcal A)$$

>[!DEFINITION] Theorie
>Die Theorie einer Struktur menge $\mathcal A$ ist:
> $$Th(\mathcal A) := \lbrace \varphi : \mathfrak S \vDash \varphi \text{ for all } \mathfrak S \in \mathcal A\rbrace$$



## Vollständig

Eine Theorie $T$ ist __vollständig__, wenn jeder Satz oder seine Negation in $T$ ist.

>[!SENTENCE] Satz
>Eine [axiomatisierbare](Axiomatisierung.md) und vollständige Theorie ist [entscheidbar](Entscheidbar.md)


---

>[!SENTENCE]
>Eine [axiomatisierbare](Axiomatisierung.md) und vollständige Theorie ist [entscheidbar](Entscheidbar.md)

Daher genügt es nach der Axiomatisierung, die Vollständigkeit der Theorie zu beweisen, um daraus Entscheidbarkeit abzuleiten.


## Beispiele
- Die Theorie aller unendlichen linearen Ordnungen mit Endpunkten
- Die Theorie aller Graphen
- Die Theorie aller Arrays




