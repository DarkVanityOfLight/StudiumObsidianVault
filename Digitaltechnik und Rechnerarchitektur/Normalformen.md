
## Grundlegende Definitionen

- **Literal**: Ein Literal ist entweder eine Variable oder die Negation einer Variable: 
  $$LV := V ∪ \{\neg x \mid x \in V\}$$
  
- **Minterm**: Ein Minterm ist eine Konjunktion von Literalen, die alle Variablen in V verwendet.

- **Maxterm**: Ein Maxterm ist eine Disjunktion von Literalen, die alle Variablen in V verwendet.

- **Monom**: Ein Monom ist eine Konjunktion von Variablen aus $\vartheta ⊆ V$.

- **Würfel (Cube)**: Ein Würfel ist eine Konjunktion von Literalen $L\vartheta$ mit $\vartheta \subseteq V$.

- **Klausel**: Eine Klausel ist eine Disjunktion von Literalen $L\vartheta$ mit $\vartheta \subseteq V$.

## Kanonische Formen

- **DNF (Disjunktive Normalform)**: Eine DNF ist eine Disjunktion von Würfeln.

- **CNF (Konjunktive Normalform)**: Eine CNF ist eine Konjunktion von Klauseln.

- **RMNF (Reduzierte Minterm-Normalform)**: Eine RMNF ist eine exklusive Disjunktion von Monomen.

- **Gemischt-polarisierte RMNF**: Eine gemischt-polarisierte RMNF ist eine exklusive Disjunktion von Würfeln.


## Darstellung von DNF und CNF

- **DNF (Disjunktive Normalform)**: Eine DNF kann als eine Menge von Mengen von Literalen gespeichert werden, wobei alle Variablen in jedem Literal vorkommen müssen.

- **CNF (Konjunktive Normalform)**: Eine CNF kann ebenfalls als eine Menge von Mengen von Literalen gespeichert werden, wobei alle Variablen in jedem Literal vorkommen müssen.

## Speicherung von RMNF

- **RMNF (Reduzierte Minterm-Normalform)**: Eine RMNF kann als eine Menge von Mengen von Variablen gespeichert werden. Dabei gelten folgende Zuordnungen:
  - $\{\} :\equiv 0$
  - $\{\{\}\} :\equiv 1$
  - $\{\{x\}\} :\equiv x$
  - $\{\{\}, \{x\}\} :\equiv \neg x$

Beachten Sie, dass die Variablenmenge V eine spezielle Bedeutung hat:
  - $\{\} :\equiv 1$ (leeres Set entspricht der Konstante 1)
  - $W_{\{\}} :\equiv 0$ (leeres Set entspricht der Konstante 0)
  - $L_{\{\}} :\equiv 0$ (leeres Set entspricht der Konstante 0)

Die Kanonizität dieser Formen ergibt sich aus der Betrachtung der möglichen nicht-äquivalenten Fälle, wobei für alle kanonischen Normalformen insgesamt $2^{2^n}$ nicht-äquivalente Fälle betrachtet werden müssen.

