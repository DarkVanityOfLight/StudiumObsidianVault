Gegeben zwei (aussagenlogische) Formeln $F$ und $G$, wir sagen dass $F$ eine
_Teilformel_ von $G$ ist, falls $F$ ein Teilbaum des Parsebaums der Formel
$G$ ist. Zum Beispiel, $(x \land y)$ ist eine Teilformel von ($x \land y) \land z$,
 $(x \lor y)$ aber nicht. $(y \land x)$ ist auch keine Teilformel von $(x \land y) \land z$ .
Äquivalenz lässt sich der Begriff der Teilformel rekursiv definieren. Genauer gesagt, wir definieren eine Funktion $sub: PROP \to 2^{PROP}$ wie folgt. 

**Basisfälle (Induktionsanfang)**:
- Fall 1: $sub(\top) := {\top}$
- Fall 2: $sub(\bot) := {\bot}$
- Fall 3: $sub(x) := {x}$
**Induktive Fälle (Induktionsschritt)**:
- Fall 1: $sub(\neg F) := \neg sub(F)$
- Fall 2: $sub(F \land G) := {F \land G} \cup sub(F) \cup sub(G)$
- Fall 3: $sub(F \lor G) := {F \lor G} \cup sub(F) \cup sub(G)$
