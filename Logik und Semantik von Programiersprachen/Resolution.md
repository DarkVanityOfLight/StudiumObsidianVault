
Unser Ziel ist es den Nachweis der [Gültigkeit](Gültig.md) einer [aussagenlogischen](Aussagenlogik.md) Formel auf leicht automatisierbare syntaktische Manipulationen zu reduzieren.

## Darstellung von KNF Formeln als Mengen

Eine [Klausel](Klausel.md) kann als [Menge](Mengen.md) dargestellt werden, da $\lor$  [kommutativ](Kommutativgesetz.md), [assoziativ](Assoziativgesetz.md) und [Idempotent](Axiome%20der%20Boolschen%20Algebra.md#Idempotenz) ist. Auf ähnlicher Weise kann eine Konjunktion von Formeln als [Menge](Mengen.md) von Literal mengen dargestellt werden.

$$(p\lor \neg q) \land (r \lor q \lor \neg t) \land (\neg r)\land (\neg p)$$
$$\lbrace\lbrace p, \neg q\rbrace, \lbrace r, q, \neg t\rbrace, \lbrace\neg r\rbrace, \lbrace\neg p\rbrace\rbrace$$

## Resolvente

Gegeben sind zwei [Klauseln](Klausel.md) $C$ und $C'$ mit:
1. $l\in C$ und
2. $\neg l \in C'$,
3. wobei $l$ ein [Literal](Literal.md) ist.

Folgendes nennt man eine Resolvente von $C$ und $C'$
$$R = C \setminus \lbrace l\rbrace \cup C' \setminus \lbrace\neg l \rbrace$$


## Resolution Prozedur

Angenommen $F$ wäre eine [Menge](Mengen.md) von Klauseln

$$Res(F) := F \cup \lbrace R : R \text{ is a resolvent of } F\rbrace$$


$$Res^0(F) := F$$
$$Res^{n+1}(F) := Res(Res^n(F))$$
$$Res^*(F) := \bigcup_{n\ge 0} Res^n(F)$$

![resolution.excalidraw](resolution.excalidraw.md)

Diese Darstellung von einem Beweis als Baum wir auch Beweisbaum genannt, ist oft einfach nachzuvollziehen, im Vergleich zu der Beweissequenz 
$$\lbrace p, \neg q\rbrace\lbrace r, q\rbrace \lbrace\neg r\rbrace\lbrace\neg p\rbrace \lbrace q\rbrace\lbrace p\rbrace\bot$$

Das Resolution-Beweissystem erfüllt alle erwünschten Eigenschaften eines [Beweissystems](Beweissystem.md)

