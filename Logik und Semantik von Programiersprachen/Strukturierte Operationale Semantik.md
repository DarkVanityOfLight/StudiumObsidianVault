
Strukturierte operationale Semantik ist eine Methode, die einem Programm Bedeutung zuordnet, wobei die Zustandsänderung des Programms durch Einzelne Programmschritte präzise definiert wird.

SOS ist eine Semantik, die der Ausführung eines Programms ähnelt.

## Datentyp

Wir beschränken uns auf Programme, die auf [ganzen Zahlen](Ganze%20Zahlen.md) arbeiten. Dazu benutzen wir die Theorie der [Ganzzahlige lineare Arithmetik](Logik%20und%20Semantik%20von%20Programiersprachen/Ganzzahlige%20lineare%20Arithmetik.md) zum definieren der Semantik von WHILE:

$$\mathcal Z := (\mathbb Z; +, \cdot, 0, 1)$$
Der Bequemlichkeit halber verwenden wir die folgende unäre Funktion
$$- : \mathbb Z \to \mathbb Z \qquad - : n \mapsto (-1 \cdot n)$$

## Bewertung

Wir gebrauchen die Definition von [Bewertungen](Logik%20und%20Semantik%20von%20Programiersprachen/Bewertung.md) aus der [Prädikatenlogik](Logik%20und%20Semantik%20von%20Programiersprachen/Prädikatenlogik.md) 
$$\nu : \text{VAR} \to \mathbb Z$$
unter anderem, lässt sich eine Bewertung als ein Programmzustand zu einem bestimmten Zeitpunkt betrachten.

## Programmzustände
Ein __Programmzustand__ ist ein Schnappschuss eines laufenden Programmes.

Es gibt zwei Arten von Programmzuständen:

1. Zwischenzustand $$\langle S, \nu\rangle$$ wobei $S$ eine Anweisung bzw. $\nu$ eine Bewertung ist(bez. der freien Variablen von $S$)
2. Finalzustand $$\nu$$ wobei $\nu$ eine Bewertung ist.


## Die Beweisregeln

_[SKIP]_
$$\langle \text{skip}, \nu \rangle \implies \nu$$

_[ASG]_
$$\langle x := t, \nu\rangle \implies \nu[\text{val}_{\nu}(t)/x]$$
_[SEQ1]_
$$\langle S_1, \nu \rangle \implies \langle S'_1, \nu_1'\rangle\over{\langle S_1; S_2, \nu\rangle \implies \langle S'_1; S_2, \nu'\rangle}$$
_[SEQ2]_
$$\langle S_1, \nu \rangle \implies \nu'\over{\langle S_1; S_2,\nu \implies \langle S_2, \nu'\rangle}$$

_[IF1]_
$$\langle\text{if }\varphi\text{ then }S_1 \text{ else } S_2, \nu\rangle \implies \langle S_1, \nu\rangle \qquad \text{ falls } \mathcal Z, \nu \vDash \varphi$$

[IF2]
$$\langle\text{if }\varphi\text{ then }S_1 \text{ else } S_2, \nu\rangle \implies \langle S_2, \nu\rangle \qquad \text{ falls } \mathcal Z, \nu \vDash \neg\varphi$$
[W]
$$\langle \text{while }\varphi \text{ do } S, \nu\rangle \implies \langle\text{if }\varphi \text{ then } (S; \text{while } \varphi \text{ do } S) \text{ else skip}, \nu\rangle$$
