


>[!DEFINITION] Theorem
>Gegeben sei ein [SNF](Normalformen%20der%20Prädikatenlogik.md#Skolemnormalform(SNF))-[Satz](Satz.md) $\varphi \forall x_1, \dots, x_n \psi$,
>dann ist er erfüllbar genau dann wenn er ein [[Herbrand-Modell]] hat.


## Beispiel

$$\exists x, y, z ((P(x) \to P(y)) \land (P(y) \to P(z) \land \neg P(z)))$$

Skolemisiere:
$$(P(a) \to P(b)) \land (P(b) \to P(c) \land \neg P(c))$$

Das Herbrand-Modell hat das Universum $\lbrace a, b, c\rbrace$

