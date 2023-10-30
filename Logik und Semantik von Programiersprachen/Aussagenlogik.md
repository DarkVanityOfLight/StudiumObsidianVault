
Eine aussagenlogische Formel ist eine Zeichenkette über das Alphabet $$\Sigma = \mathcal V \cup \mathcal C \cup O \cup P$$

1. $\mathcal V = \lbrace p, q, x, y\rbrace$, Menge von Variablen
2. $\mathcal C = \lbrace \top, \bot\rbrace$, Menge von Konstanten
3. $\mathcal O = \lbrace \neg, \land, \lor$, Mege von Verknüpfungen
4. $\mathcal P = \lbrace (,)\rbrace$, Menge von Klammerzeichen.

> [!NOTE] EIne Variable wird auch als atomare Aussage bezeichnet

## Syntax

Eine aussagenlogische Formel $\varphi$ wird durch Rekursion definiert:

1. Eine Variable $x$ ist eine Formel
2. Eine Konstante (d.h. $\top$ oder $\bot$) ist eine Formel
3. Für Formeln $\varphi_1, \varphi_2$ sind die Folgenden auch Formeln:
$$(\neg \varphi_1)\, (\varphi_1 \land \varphi_2)\, (\varphi_1 \lor \varphi_2)$$

Dies lässt sich als BNF-Grammatik zusammenfassen:
$$\varphi ::= \top | \bot | (\neg\varphi) | (\varphi \land \varphi) | (\varphi\lor\varphi)$$

>[!IMPORTANT] $PROP$ bezeichnet die Menge aller aussagenlogischen Formeln


