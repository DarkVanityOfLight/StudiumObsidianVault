Normalformen sind wichtig in der Algebra. Zum Beispiel, wenn man mit Polynomen arbeitet, eine Darstellung als eine Summe von Termen ist erwünscht.
D.h., man würde die Darstellung

$$
8x^9 + 7x^4 + 7x^3 + 7x^2 + 7x
$$

gegenüber

$$
7(x+x^2(x^7 + x^2 + 1) + x^3) + x^9
$$

bevorzugen.

Die Ausdrücke in einer Normalform sehen nicht nur einfacher aus, sondern es ist auch einfacher mit diesen Ausdrücken zu arbeiten (Beispiel: vergleiche zwei Polynome). Wir werden drei Normalformen kennenlernen: 
1. Negationsnormalform (NNF)
2. Konjunktive Normalform (CNF)
3. Disjunktive Normalform (DNF)

## Negationsnormalform (NNF)

**Definition**: Ein _Literal_ ist entweder eine Variable $x$, oder deren Negation $\neg x$.
Das Literal $x$ nennt man _positiv_, während $lnot x$ ein
_negatives_ Literal ist.

Eine Aussagenlogische Formel $F$ ist in _Negationsnormalform (NNF)_ falls sie von der Form
1. $l$ ist, wobei $l$ ein Literal ist, oder,
2. $G \land H$, wobei $G$ und $H$ Formeln in NNF sind, oder
3. $G \lor H$, wobei $G$ und $H$  bereits in NNF sind.

Mit anderen Worten, eine Formel ist in NNF gdw. jede vorkommende Negation direkt vor einer Variable auftritt.
Beispielsweise ist die folgende Formel in NNF:

$$
(p \land \lnot q) \lor (\lnot p \lor \lnot a).
$$

Im Gegensatz dazu ist diese Formel _nicht_ in NNF:

$$
(p \land \lnot(q \lor r)) \land \lnot\lnot a.
$$

**Satz**: Für jede Aussagenlogische Formel existiert eine äquivalente Formel in NNF.

Um diesen Satz zu beweisen, genügt es zu zeigen, wie man eine beliebige Formel in NNF umwandelt. Der Beweis der Korrektheit ist dem Leser als eine leichte Übung überlassen. In der gegebenen Formel soll zunächst jedes Vorkommen von \bot bzw. \top entfernt oder durch $(x \land \lnot x)$ bzw. $(x \lor \lnot x)$ ersetzt. Danach sollen alle Negationen reingezogen werden, indem man wiederholt die [De Morgansche Gesetze](Axiome%20der%20Boolschen%20Algebra.md) anwendet. Wir bekommen eine äquivalente Formel in NNF.

Dies war ein informaler Überblick über wie der Algorithmus funktionert. Vollständigkeitshalber diskutieren wir den Algorithmus $nnf(.)$ im Detail:

Gegeben eine Formel $F$, der Algorithmus $nnf(F)$ berechnet eine äquivalente Formel in NNF wie folgt:
1. Falls $F = x$, wobei $x$ eine Variable ist, gebe $x$ zurück.
2. Falls $F = G \land H$, wobei $F$ und $H$ Formeln sind, gebe $nnf(G) \land nnf(H)$ zurück.
3. Falls $F = G \lor H$, wobei $F$ und $H$ Formeln sind, gebe $nnf(G) \lor nnf(H)$ zurück.
4. Falls $F = \lnot G$, wobei $G$ eine Formel ist, machen wir eine Fallunterscheidung über die Struktur von $G$.
   1. $G = x$ (eine Variable). Dann gebe $(\lnot x)$ zurück.
   2. $G = H \land H'$. Gebe $nnf(\lnot H) \lor nnf(\lnot H')$ zurück.
   3. $G = H \lor H'$. Gebe $nnf(\lnot H) \land nnf(\lnot H')$ zurück.
   4. $G = \lnot H$. Gebe $H$ zurück.


## Konjunktive Normalform (CNF)

Eine Formel nennt man eine Klausel, wenn sie eine Disjunktion von Literalen ist:


$$\bigvee_{i=1}^n \ell_i$$

Wir erlauben auch _n = 1_, jeder Literal ist also auch eine Klausel. Wir erlauben auch _n = 0_,
die (leere) Disjunktion wird in diesem Fall als \bot interpretiert. [Analog zu der leeren Summe, die üblicherweise als 0 interpretiert wird]

Eine Formel ist in _konjunktiver Normalform (CNF)_, falls sie eine Konjunktion von Klauseln ist:

$$
\bigwedge_{i=1}^n C_i
$$

Hier, $C_i$ ist eine Klausel. Ähnlich zu Disjunktionen, wir erlauben auch den Fall
$n = 0$, die (leere) Konjunktion wird in diesem Fall als \top interpretiert.
\[Analog zu dem leeren Produkt, das üblicherweise als 1 interpretiert wird\]

Beispielsweise ist die folgende Formel in CNF:

$$((p \lor q) \land (\lnot p \lor \lnot r \lor a))$$

**Satz**: Für jede Formel gibt es eine äquivalente CNF Formel.

Dieser Satz ist korrekt, etwa wegen der Distributivität von Konjunktionen und Disjunktionen. Leider würde hier eine einfacher Induktiver Beweisansatz nicht wirklich funktionieren, da die Induktionsvoraussetzung zu schwach ist. Um dieses Problem zu beheben, führen wir die disjunktive Normalform ein, sodass dann die starke Induktionsvoraussetzung uns sagt, dass jede Formel äquivalente Formeln sowohl in CNF als auch in DNF hat.

## Disjunktive Normalform (DNF)

Man nennt eine Formel ein _Term_, falls sie eine Konjunktion von Literalen ist. Eine Formel ist in disjunktiver Normalform, falls sie eine disjunktion von Termen ist:

Beispielsweise ist die folgende Formel in DNF:

$$((p \land \lnot q \land a) \lor (p \land r))$$

**Satz**: Eine Formel ist in CNF gdw. ihre Negation in DNF ist.

_Beweis_: Sei $F$ eine Formel in CNF. $(nnf(\lnot F))$ ist eine äquivalente DNF Formel. Der Beweis in die andere Richtung ist analog. (QED)

**Satz**: Für jede Formel $F$ gibt es eine äquivalente Formel $cnf(F)$ in CNF, und eine Formel $dnf(F)$ in DNF.

_Beweis_: Der Beweis ist mit Induktion über $F$.
Induktionsanfang: $(\bot), (\top), (x)$ sind bereits sowohl DNF als auch CNF Formel.
Induktionsschritt:

  - Fall $F = \lnot G$. Nach der Induktionsvoraussetzung sind $dnf(G) $und $cnf(G)$beide definiert. Die Formel $(nnf(\lnot cnf(G))) (bzw. (nnf(\lnot dnf(G))))$ ist in CNF (bzw. DNF). Definiere also $(dnf(F) := nnf(\lnot cnf(G)))$ und $(cnf(F) := (\lnot nnf(dnf(G))))$.
  - Fall $F = G \land H$. Definiere $(cnf(F) := cnf(G) \land cnf(H))$. Wir bemerken, dass dies eine äquivalente CNF Formel ist. Sei $(dnf(G) = S_1 \lor ... \lor S_n)$ $(dnf(H) = T_1 \lor ... \lor T_m)$ Definiere $(dnf(F))$ wie folgt: $(dnf(F) = \bigvee_{i \in {1,...,n}, j \in {1,...,m}}(S_i \land T_j))$
  - Fall $F = G \lor H$. Analog zu dem Fall$F = G \land H$.
$\blacksquare$

## Ausdrucksstärke der Aussagenlogik

Wir haben bereits gesehen, dass jede aussagenlogische Formel als eine Boolsche Funktion interpretiert werden kann. Nun stellt sich die Frage, ob die Umkehrung auch gilt? Es ist tatsächlich so, dass es für jede _endliche boolsche Funktion_ eine Aussagenlogische Formel gibt, die diese Funktion ausdrückt.
Eine boolsche Funktion

$$
f: \{0,1\}^V \rightarrow \{0,1\}
$$

heißt endlich, falls die Menge der "relevanten" Variablen _endlich_ ist. Eine Variable $x$ heißt
_relevant_ in $f$, falls es zwei Interpretationen $(I,I': V \rightarrow \{0,1\})$gibt
sodass$(I(x) \neq I'(x)) und (f(I) \neq f(I'))$.

**Satz**: Jede endliche boolsche Funktion $f: \{0,1\}^n \rightarrow \{0,1\}$ kann als aussagenlogische Formel dargestellt werden.

_Beweis_: Wir konstruieren eine Disjunktion von Termen, die äquivalent zu $f$ ist.
Jedes Term $((l_1 \land ... \land l_n))$ entspricht einer Interpretation

$(\nu: \{x_1,...,x_n\} \rightarrow \{0,1\})$
wobei wir das Literal $(l_i)$ positiv machen, wenn $(\nu(x_i) = 1)$, und negativ andernfalls.
Falls $(f(\nu) = 1)$, dann fügen wir diesen Term zu der DNF hinzu.
$\blacksquare$
