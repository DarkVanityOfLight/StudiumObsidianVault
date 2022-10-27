Funktion: jedem wert des Definitionsbereichs muss ein wert zugewiesen sein, die Zuweisung muss eindeutig sein
Relation:

## Notation endlicher Abbildungen
Sind X und Y [Mengen](Mengen.md) dann bezeichnet $X\to_{fin} Y$ die Menge aller endlichen Abbildungen von X nach Y.

Ist $\phi \in X\to_{fin} Y$, dann bezeichnet $dom \phi \subseteq$ die Menge aller Elemente aus X, auf denen $\phi$ definiert ist, den Definitionsbereich von $\phi$. Der Definitionsbereich $dom \phi$ muss endlich sein.
Die Anwendung einer endlichen Abbildung $\phi$ auf eine Element x notieren wir mit

### Leere Abbildung $\emptyset$
$dom \emptyset := \emptyset$
### Einelementige Abbildung(Bindung) $\{x \mapsto y\}$
$dom \{x\mapsto y\}:= \{x\}$
$\{x\mapsto y\}(x) := y$
d
### Erweiterug von $\phi_1$ um $\phi_2$ notiert $\phi_1, \phi_2$(Kommaoperator)

$dom(\phi_1, \phi2) := dom \phi_1 \cup dom \phi_2$
$$(\phi_1, \phi_2)(x):= \left\{{\phi_2(x)\ falls x \in dom \phi_2
\atop \phi_1(x)\ sonst}\right.$$