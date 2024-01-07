
Eine __Theorie__ ist eine [Satzmenge](Satz.md) mit einer bestimmten [Signatur](Logik%20und%20Semantik%20von%20Programiersprachen/Signatur.md). Gegeben sei $\mathcal A$ eine $\sigma$-[Struktur](Struktur.md). Definiere die __Theorie__ von $\mathcal A$:
$$Th(\mathcal A) := \lbrace \varphi : \mathcal A \vDash \varphi\rbrace$$

Sei $\mathcal S$ eine [Menge](Mengen.md) von $\sigma$-Strukturen. Definiere die __Theorie__ von $\mathcal S$:
$$Th(\mathcal S) := \bigcap_{\mathcal A \in\mathcal S} Th(\mathcal A)$$

## Beispiele
- Die Theorie aller unendlichen linearen Ordnungen mit Endpunkten
- Die Theorie aller Graphen
- Die Theorie aller Arrays

