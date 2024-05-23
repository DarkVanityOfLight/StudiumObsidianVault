Eine Formel $\varphi$ ist bereinigt, wenn es für jede Variable $x$ gilt, dass (I) alles Vorkommen von $x$ in $\varphi$ entweder nur frei oder nur gebunden ist, und (II) $x$ in höchstens einem Quantor vorkommt.

Die Formel 
$$\exists xR(x) \land \exists R'(x)$$
ist nicht bereinigt, da $x$ in zwei anderen Quantoren vorkommt. Ähnlicher weise ist die Formel $\varphi := \forall x(x\not = x+1) \land \exists y(x=y)$ nicht bereinigt, weil sowohl ein freies Vorkommen als auch ein gebundenes Vorkommen von $x$ in $\varphi$ existieren.

>[!DEFINITION] Proposition
>Es gibt einen Algorithmus, der eine gegebene Formel in eine bereinigte Formel mit linearer Größe umwandeln kann.

