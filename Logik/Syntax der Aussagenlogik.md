Eine aussagenlogische Formel $\varphi$ wird durch Rekursion definiert:

1. Eine Variable $x$ ist eine Formel
2. Eine Konstante (d.h. $\top$ oder $\bot$) ist eine Formel
3. Für Formeln $\varphi_1, \varphi_2$ sind die Folgenden auch Formeln:
$$(\neg \varphi_1)\, (\varphi_1 \land \varphi_2)\, (\varphi_1 \lor \varphi_2)$$

Dies lässt sich als BNF-Grammatik zusammenfassen:
$$\varphi ::= \top | \bot | (\neg\varphi) | (\varphi \land \varphi) | (\varphi\lor\varphi)$$

>[!IMPORTANT] $PROP$ bezeichnet die Menge aller aussagenlogischen Formeln
