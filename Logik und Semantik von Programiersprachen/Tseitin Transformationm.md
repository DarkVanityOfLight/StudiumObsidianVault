
Die naive Transformation von einer Aussagenlogischen Formel nach [CNF](Normalformen%20in%20der%20Aussagenlogik.md#Konjunktive%20Normalform%20(CNF)) kann ein exponentielles Blowup verursachen. Dies wollen wir gerne vermeiden, d.h. unser Ziel ist es eine effiziente Reduktion zu konstruieren. Genau so eine Reduktion nimmt eine Formel und produziert eine andere Formel, die [erfüllbarkeitsäquivalent](Erfüllbarkeitsäquivalent.md) zu der ursprünglichen Formel ist. Die Größe der von der Tseitin Transformation produzierten Formel ist linear in der Größe der ursprünglichen Formel.
Wir nehmen an, dass unsere Eingabeformeln bereits in [Negationsnormalform (NNF)](Normalformen%20in%20der%20Aussagenlogik.md#Negationsnormalform%20(NNF)) sind und nur die Operatoren $\lbrace \neg, \land, \lor\rbrace$ enthalten. Wir erinnern uns auch an die rekursive Definition von der Menge $SUB(\varphi)$ der [Teilformel](Teilformeln.md) der Formel $\varphi$:
- $SUB(x) = \lbrace x \rbrace$
- $SUB(\neg \varphi) = \lbrace \neg \varphi \rbrace \cup SUB(\varphi)$
- $SUB(\varphi \circ \psi) = \lbrace \varphi \circ \psi \rbrace \cup SUB(\psi)\rbrace$, wobei $\circ \in \lbrace \land, \lor\rbrace$

> [!DEFINTION] Minimales nicht-Literal 
> Eine Teilformel $\psi$ von $\varphi$  nennt man ein minimales nicht-Literal, falls $\psi$ von der Forml $l \circ l'$ ist, wobei $l$ und $l'$ Literale sind und $\circ \in \lbrace \land, \lor\rbrace$.

Die Tseitin Transformation assoziiert [rekursiv](Rekursion) eine neue Variable $X$ zu einer Teilformel $\psi$, die ein minimales nicht-Literal ist. Dann wird eine [Äquivalenz](Äquivalenz.md) von dieser Variable $X$ und $\psi$ als [Menge](Mengen.md) von [Klauseln](Klausel.md) ausgedrückt. Genauer gesagt, wir verwalten eine Menge $C$ von Formeln (wir starten mit $C = \emptyset$), indem wir rekursiv eine Teilformel von $\varphi$, die ein minimales nicht-Literal der Form $l\circ l'$ ist, betrachten, und diese durch eine neue Variable $X$ ersetzen. Dabei fügen wir gleichzeitig eine zur $X\leftrightarrow l\circ l'$ äquivalente Menge $S$ von Klauseln zu $C$ hinzu.
In diesem Fall $\circ = \land$ besteht diese Menge $S$ aus den folgenden Klauseln
$$(\neg X \lor l), (\neg X \lor l'), (\neg l \lor \neg l' \lor X)$$
Falls $\circ = \lor$, dann enthält $S$ die folgenden drei Klauseln:
$$(\neg X \lor l \lor l'), (\neg l \lor X), (\neg l' \lor X)$$

Man kann überprüfen, dass die Konjunktion von Klauseln aus $S$ tatsächlich äquivalent zu $X \leftrightarrow l \circ l'$ ist. Die Prozedur terminiert, falls $\varphi$ keine Teilformeln, die minimale nicht-Literale sind, mehr hat(mit anderen Worten, wenn $\varphi$ einfach ein Literal ist).


>[!NOTE] Theorem
>Die Tseitin Transformation garantiert, dass die urspruengliche Formel erfuellbar ist genau dann wenn, die produzierte Formel erfuellbar ist.

>[!NOTE] Lemma
>Sei $\psi$ eine Teilformel von $\varphi$, und $X$ eine Variable die nicht in $\varphi$ vorkommt. Wir definieren weiterhin
>$$\varphi' := \varphi[X/\psi] \land (X \leftrightarrow \psi)$$
>Dann, für jede [Belegung](Belegung.md) $I \vDash X \leftrightarrow \psi$, haben wir
>$$I\vDash \varphi \iff I\vDash \varphi'$$
>Insbesondere gilt, dass $\varphi$ erfüllbar ist genau dann wenn $\varphi'$ erfüllbar ist.

__Beweis__

Betrachte eine Belegung $I \vDash X \leftrightarrow \psi$. Es folgt, dass $I\vDash X$ genau dann wenn $I\vDash \psi$. Der [Substitutionssatz](Substitutionssatz.md) impliziert $I \vDash \varphi[X/\psi]$ genau dann wenn $I\vDash \varphi$. Also, aus $I\vDash \varphi$ folgt $I \vDash \varphi'$. Für die andere Richtung nehmen wir $I\vDash \varphi'$ an. Dann gilt $I\vDash \varphi[X/\psi]$ und mit dem [Substitutionssatz](Substitutionssatz.md) $I \vDash \varphi$.
Um zu zeigen, dass $\varphi$ erfüllbar ist genau dann wenn $\varphi'$ erfüllbar ist, reicht es die Belegung $I$ wie folgt zu definieren: $I(X) = 1$ genau dann wenn $I\vDash \varphi$
$\blacksquare$

__Größe der produzierten Formel__  Die Tseitin Transformation fügt höchstens so viele neue Variablen hinzu, wie es Teilformeln in $\varphi$ gibt. Die Ausgabeformel hat ungefähr $3n$ Klauseln, wobei $n$ die Anzahl der Teilformeln der ursprünglichen Formel ist. Die Größe der Ausgabeformel ist also linear in der Größe der ursprünglichen Formel. Eine naive Implementierung würde hier quadratische Laufzeit haben, aber man kann dies zu einer linearen Laufzeit verbessern.

>[!NOTE]
>Die Tseitin Transformation kann jederzeit gestoppt werden, falls $\varphi_i$ schon in CNF vorliegt. Es ist unerheblich für die Transformation und deren Korrektheit, in welcher Reihenfolge die Teilformeln durch Variablen ersetzt werden. Eine gute Implementierung der Tseitin Transformation würde also versuchen, die Anzahl der Ersetzungen zu minimieren.

## Beispiel

Sei $\varphi = \neg x \lor (y\land z)$. Ursprünglich haben wir $\varphi_0 = \varphi$ und $C_0 = \emptyset$. Im ersten Schritt ersetzen wir $y\land z$ durch eine neue Variable $X_1$ und erhalten $\varphi_1 = x \to X_1$ und $C_1 = \lbrace \neg X_1 \lor y, \neg X_1 \lor z, \neg y \lor \neg z \lor X_1 \rbrace$. Im zweiten Schritt ersetzen wir $\neg x \lor X_1$ durch eine neue Variable $X_2$ und fügen  $\neg X_2 \lor \neg x \lor X_1, x \lor X_2, \neg X_1 \lor X_2$ zu $C$ hinzu. An dieser Stelle erhalten wir also $\varphi_2 =X_2$ und $C_2 = \lbrace \neg X_1 \lor y, \neg X_1 \lor z, \neg y \lor \neg z \lor X_1, \neg X_2 \lor \neg x \lor X_1, x \lor X_2, \neg X_1 \lor X_2\rbrace$.
Nun enthält $\varphi_2$ keine Teilformeln mehr, die minimale nicht-Literale sind. Wir sind also fertig und die Ausgabeformel ist die Konjunktion von Klauseln in $C_2$ mit $\varphi_2$ d.h. 
$\bigwedge_{\psi \in C)2} \psi \land \varphi_2$.

