Um endliche Abbildungen zu konstruieren bzw. zu manipulieren, verwenden wir die folgende Operationen:

## Konstruktion und Manipulation endlicher Abbildungen

### Die leere Abbildung $\emptyset$
$$dom \emptyset := \emptyset$$
### Die einelementige Abbildung(auch: Bindung)
$$dom\{x \mapsto y\} := \{x\}$$
$$\{x \mapsto y\}(x) := y$$
### Die Erweiterung(Kommaoperator)
$$dom(\varphi_1, \varphi_2) := dom \varphi_1 \cup dom \varphi_2$$
$$(\varphi_1, \varphi_2)(x):= 
\left\{ \begin{align}
&\varphi_2(x)\ falls\ x \in dom \varphi_2\\
&\varphi_1(x)\ sonst
\end{align}\right.$$
Der Kommaoperator ist [assoziativ](Assoziativgesetz.md) aber nicht [kommutativ](Kommutativgesetz.md)

### Die Einschränkung
$$dom(\varphi - A) := dom \varphi - A$$
$$(\varphi - A)(x) := \varphi(x)$$
Dies endlichen Abbildungen sind mehr oder weniger gleich der [Mengen](Mengen.md) und ihrer Operationen([Differenz von zwei Mengen(Komplement)](Differenz%20von%20zwei%20Mengen(Komplement).md), [Durschnitt von zwei Mengen](Durschnitt%20von%20zwei%20Mengen.md), [Vereinigung von zwei Mengen](Vereinigung%20von%20zwei%20Mengen.md))

 ## Eigenschaften endlicher Abbildungen
[Die Erweiterung(Kommaoperator)](Endliche%20Abbildungen.md#Die%20Erweiterung(Kommaoperator)) ist [assoziativ](Assoziativgesetz.md):
$$(\varphi_1, \varphi_2), \varphi_3 = \varphi_1, (\varphi_2, \varphi_3)$$
Statt $(\varphi_1, \varphi_2), \varphi_3$ schreiben wir kurz $\varphi_1, \varphi_2, \varphi_3$. Zusätzlich verwenden wir $\{x_1 \mapsto y_1, ..., x_n \mapsto y_n\}$ als Abkürzung für $\{x_1 \mapsto y_1\}, ..., \{x_n \mapsto y_n\}$(wiederholte Anwendung des Kommaoperators).
Der Kommaoperator ist aber nicht [kommutativ](Kommutativgesetz.md): $\varphi_1, \varphi_2$ ist in der Regel nicht das Gleiche wie $\varphi_2, \varphi_1$
$$
\{Ralf \mapsto Pizza\}, \{Ralf \mapsto Saltimbocca\} = \{Ralf \mapsto Saltimbocca\}
$$
$$
\{Ralf \mapsto Saltimbocca\}, \{Ralf \mapsto Pizza\} = \{Ralf \mapsto Pizza\}
$$
