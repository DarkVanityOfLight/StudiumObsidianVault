
Zwei Formeln $\varphi, \psi$ sind äquivalent $\varphi \equiv \psi$, wenn 
$$[[\varphi]] = [[\psi]]$$


>[!DANGER]  Vorsicht
>Die Symbolde $\equiv, =, :=$ sind absichtlich mehrdeutig



## Praedikatenlogik

Sei $\sigma$ eine Signatur. Wir betrachten [prädikatenlogische](Logik%20und%20Semantik%20von%20Programiersprachen/Prädikatenlogik.md) Formeln und Strukturen, die mit $\sigma$ passen. 

Zwei Formeln $\varphi$ und $\psi$ sind äquivalent($\varphi\equiv\psi$), wenn für jede [Struktur](Struktur.md) gilt, dass $(\mathfrak S, \mathcal v) \vDash \varphi$ genau dann wenn $(\mathfrak S, \mathcal v) \vDash \psi)$. 

Die Semantische Äquivalenz ist eine [Kongruenz](Kongruent.md): Ein Ersatz von Teilformeln $\psi$ in $\varphi$ durch eine äquivalente Formel $\varphi'$ ergibt eine äquivalente Formel $\varphi'$. Unter anderen bedeutet dies, dass $F_1\lor F_2 \equiv G_1 \lor G_2$, falls $F_1 \equiv G_1$ und $F_2 \equiv G_2$ gelten. Ähnlicher weise gilt $\forall xF \equiv \forall xG$, wenn $F\equiv G$

