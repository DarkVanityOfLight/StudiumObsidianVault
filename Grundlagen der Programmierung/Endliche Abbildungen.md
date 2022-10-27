Um endliche Abbildungen zu konstruieren bzw. zu manipulieren, verwenden wir die folgende Operationen:

## Die leere Abbildung $\emptyset$
$$dom \emptyset := \emptyset$$
## Die einelementige Abbildung(auch: Bindung)
$$dom\{x \mapsto y\} := \{x\}$$
$$\{x \mapsto y\}(x) := y$$
## Die Erweiterung(Kommaoperator)
$$dom(\varphi_1, \varphi_2) := dom \varphi_1 \cup dom \varphi_2$$
$$(\varphi_1, \varphi_2)(x):= 
\left\{ \begin{align}
&\varphi_2(x)\ falls\ x \in dom \varphi_2\\
&\varphi_1(x)\ sonst
\end{align}\right.$$
Der Kommaoperator ist [assoziativ](Assoziativgesetz.md) aber nicht [kommutativ](Kommutativgesetz.md)￼###
.
## Die Einschränkung
$$dom(\varphi - A) := dom \varphi - A$$
$$(\varphi - A)(x) := \varphi(x)$$
Dies endlichen Abbildungen sind mehr oder weniger gleich der [Mengen](Mengen.md) und ihrer Operationen([Differenz von zwei Mengen](Differenz%20von%20zwei%20Mengen.md), [Durschnitt von zwei Mengen](Durschnitt%20von%20zwei%20Mengen.md), [Vereinigung von zwei Mengen](Vereinigung%20von%20zwei%20Mengen.md))

 ## Konstruktion und Manipulation endlicher Abbildungen
 