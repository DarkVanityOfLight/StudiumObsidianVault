
Die Prädikatenlogik(auch als Logik der ersten Stufe bezeichnet und meistens als FO abgekürzt) ist eine Erweiterung der [Aussagenlogik](Aussagenlogik.md) mit drei Eigenschaften. Erstens lässt sie generelle Grundmengen von Objekten zu, auf die sich die Prädikatenlogik Formel beziehen können, d.h. anstelle von nur $0$ und $1$. Diese Menge wird auch __Universum__ genannt. Zweitens ist die Prädikatenlogik imstande, Zusammenhänge zwischen Elementen in der Grundmenge zu beschreiben. Zu diesen Zweck werden __Praedikaten__(auch __Relationen__) genannt verwendet, die sich auf Elemente des [Unviversums](Universum.md) beziehen. Und nicht zuletzt verwendet FO die meistens in der Mathematik benutzten [Quantoren](Quantoren.md). Das heißt: die Logik ist in der Lage Sätze wie "für jedes Element des Universums" oder "es gibt ein Element des Universums ..." zu beschreiben. Beispielsweise können wir den Satz "everyone is loved by someone" durch die folgende Formel ausdrücken:
$$\forall x \exists y Loves(x, y)$$

## Syntax

In der Aussagenlogik haben wir eine Menge $V$ der Aussagen angenommen, aus denen aussagenlogische Formeln rekursiv aufgebaut werden. In der FO benutzen wir sowohl eine "Signatur"(siehe auch [Signatur](Mathe/Signatur.md), [Signatur](Grundlagen%20der%20Programmierung/Signatur.md)) als auch "Variablen"(der ersten Stufe), um die Formeln aufzubauen. Angenommen ist die Existenz einer abzählbare unendliche Menge $Var$ der Variablen(der ersten Stufe), die in der Regel als $x, y,z, \dots$  bezeichnet werden. 


### Term
Ein $\sigma$-Term ist entweder:
- Eine Variable $x\in Var$, oder
- das Objekt $f(t_1, \dots, t_r)$, falls $f$ ein $r$-stelliges Funktionssymbol in $\sigma$ ist und jedes $t_i$ ein $\sigma$ Term ist.

Terme über eine Signatur ohne Funktionssymbole sind entweder eine Variable oder eine Konstante.

---

Nun definieren wir $FO(\sigma)$. 

>[!WARNING]
>Oft implizit angenommen ist, dass $\sigma$ das Relationssymbol $=_{/2}$ enthält, was später als Gleichheit interpretiert wird. Dieses Symbol wird nicht explizit in der Signatur $\sigma$ angegeben. Immer wenn $\sigma$ kein Gleichheitssymbol enthält, wird dieser Sachverhalt explizit klar gemacht, z.B. indem der Begriff Prädikatenlogik ohne Gleichheitssymbol verwendet wird. 

Eine Formel in $FO(\sigma)$ ist eine der folgenden Objekte:

1. $R(t_1, \dots t_r)$ wobei $R\in \sigma$ und $t_1, \dots, t_r$ $\sigma$-Terme sind
2. $\varphi \land\psi$, wobei $\varphi, \psi \in FO(\sigma)$
3. $\varphi \lor \psi$, wobei $\varphi, \psi \in FO(\sigma)$
4. $\neg \varphi$, wobei $\varphi \in FO(\sigma)$
5. $\forall x\varphi$, wobei $x\in Var$ und $\varphi \in FO(\sigma)$
6. $\exists x\varphi$, wobei $x\in Var$ und $\varphi\in FO(\sigma)$


### Atomare Formeln

Formeln der Art $R(t_1, \dots, t_r)$ werden auch __atomare Formeln__ genannt. Beachten Sie, dass $t_1 = t_2$ ein Beispiel solcher Formeln ist. 

### Quantoren

Die Symbole $\forall$ und $\exists$ heißen Allquantor bzw. Existenzquantor. Eine Formel in $FO(\sigma)$ ohne Vorkommen von $\forall$ und $\exists$ wird auch __quantorenfrei__ genannt.


## Semantik

Die Semantik von $FO(\sigma)$ wird mit Bezug auf eine [Struktur](Struktur.md).
Um die Syntax und die Semantik deutlich zu unterscheiden, verwendet man manchmal untere/obere Indexe die auf eine Interpretation mut Bezug auf eine bestimmte Struktur bezeichnen, z.B. $0_{\mathcal N}$ bezeichnet die Zahl $0$ und $+_{\mathcal N}$ bezeichnet die Additionsfunktion der [natürliche Zahlen](Natürliche%20Zahlen.md). Zu Beginn unserer Untersuchung der Prädikatenlogik verwenden wir meistens diese zusätzlichen Symbole, sodass die Syntax und die Semantik deutlich getrennt werden. Allerdings ist es empfehlenswert auf eine solche Pedanterie zu verzichten, sobald wir eine Grundkenntnis der Prädikatenlogik erworben haben. Wenn eine Formel mit Bezug auf $\mathcal N$ evaluiert wird, quantifizieren die Quantoren über dem Universum von $\mathcal N$, d.h. der [Menge](Mengen.md) $\mathbb  N$. Beispielsweise drückt die Formel $\exists y(x + y = z \land y \not = 0)$, aus dass die Zahl $x$ kleiner als die Zahl $z$ ist. Zudem lässt sich die Unendlichkeit der Zahlen wie folgt beschreiben:
$$\exists \forall y (x< y)$$

### Interpretationsfunktion

Die Interpretationsfunktion lässt sich durch eine rekursive Definition über $\sigma$-[Terme](Term.md) erweitern. Gegeben eine [Struktur](Struktur.md) $\mathfrak S = (D, I)$ mit der Signatur $\sigma$, eine [Bewertung](Logik%20und%20Semantik%20von%20Programiersprachen/Bewertung.md) $\nu$ und ein $\sigma$-Term $t$, definieren wir rekursiv den Wert $\textbf{val}_{\mathfrak S, \nu}(t)$   (oder schlicht: $\textbf{val}(t)$) von $t$ mit Bezug auf $\mathfrak S$ und $\nu$ wie folgt:

1. Induktionsanfang(Variable $x$): $\textbf{val}(x) := \mathfrak(v)(x)$
2. Induktionsanfang(Konstantensymbol $c$): $\textbf{val}(c) := I(c)$
3. Induktionsschritt($r$-stelliges Funktionssymbol $f$): $$\textbf{val}(f(t_1, \dots, t_{r})) := I(f)(\textbf{val}(t_1), \dots, \textbf{val}(t_r))$$
---

Die Semantik der $FO$ ist komplizierter als die der [Aussagenlogik](Aussagenlogik.md). Denn: Wie beweist man, dass $\mathfrak S, \nu \vDash \varphi$, wobei die [Struktur](Struktur.md) $\mathfrak S$ ein unendliches [Universum](Universum.md) hat. Wie wir sehen werden, gibt es keine Algorithmus, welcher dieses Problem für alle Fälle lösen kann. Dies steht im Gegensatz zur Aussagenlogik, deren Erfüllbarkeitsproblem mithilfe von verschiedenen Methoden gelöst werden kann. Trotz der Abwesenheit eines generellen Algorithmus für die Erfüllbarkeitsproblematik lässt sich die Methode der semantischen Argumente gebrauchen, um  $(\mathfrak S, \nu) \vDash \varphi$ zu beweisen.

## Beispiel

Wir wollen $(\mathcal N, \nu) \vDash \forall x\exists y(x<y)$ beweisen. Hier ordnet $\nu$ jeder Variable das Element $0_{\mathcal N}$ zu. Zunächst einmal betrachten wir eine beliebige Zahl $n\in\mathbb N$. Unser Ziel ist, dass die Behauptung $(\mathcal N, \nu_{[n/x]}) \vDash \exists y(x<y)$ bewiesen werden muss. Zu diesem Zweck genügt es zu beweisen, dass es eine Zahl $m\in\mathbb N$ gibt, welche
$$(\mathcal N, \nu_{[m/y, n/x]}) \vDash y$$
erfüllt. Der Beweis ist leicht: die Zahl kann als $n +_{\mathcal N} 1_{\mathcal N}$ ausgewählt werden. Daraus folgt, dass $(\mathcal N, \nu) \vDash \forall x\exists y(x < y)$.

## Freie Variablen

Variablen die nicht durch einen [Quantor](Quantoren.md) gebunden sind nennen wir "frei". Der Wert einer Formel hängt nicht von der [Bewertung](Logik%20und%20Semantik%20von%20Programiersprachen/Bewertung.md) für gebundene Variablen ab.

Wir definieren Frei rekursiv. Mit der Notation $Var(\varphi)$ bezeichnen wir die Menge aller Variablen in $\varphi$. Die Menge $FREE(\varphi)$ der freien Variablen in $\varphi$ wird wie folgt definiert:
1. $FREE(R(t_1, \dots  t_n)) = \bigcup^n_{i=1} FREE(t_i)$
2. $FREE(t_1 = t_2) =  FREE(t_1) \cup FREE(t_2)$
3. $FREE(\varphi \circ \sigma) =  FREE(\varphi) \cup FREE(\psi)$, wobei $\circ\in\lbrace\land,\lor\rbrace$ 
4. $FREE(\neg \varphi) = FREE(\varphi)$
5. $FREE(Qx\varphi) = FREE(\varphi)\setminus\lbrace x\rbrace$, wobei $Q\in \lbrace \forall, \exists\rbrace$ 

Noch fehlt die Definition einer freien Variable in Termen, welche auch induktiv definiert wird:
1. $FREE(x) = \lbrace x\rbrace$
2. $FREE(c) =  \emptyset$
3. $FREE(f(t_1, \dots, t_r)) = \bigcup^r_{i=1} FREE(t_i)$
