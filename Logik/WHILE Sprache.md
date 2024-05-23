Beim betrachten von Programmiersprachen, genügt eine einfache Sprache zur Untersuchung:

```
if (x < y) then
	z := y
else
	z := x
```

```
l := x
x := y
y := l
```

```
y := 1
while (x > 0) do
	y := x * y
	x := x - 1
```

> Die WHILE Sprache enthält: Branching, Schleifen, Variable-Scoping, Ganzzahlige, Variablen/Operatoren

## Syntax

Wir nehmen die Existenz abzaehlbar vieler Variablen an
$VAR := \lbrace x_1, x_2, \dots, y_1, y_2, \dots, z_1, z_2, \dots \rbrace$

manche von ihnen werden als "lokale Variablen" bezeichnet:
$VAR_l := \lbrace l_1, l_2, \dots, l_a, l_b,\dots \rbrace$

> [!DEFINITION]
> Ein Programm ist ein Objekt, das durch folgende Grammatik $S$ erzeugt wird.

$S ::= x:=t | \text{skip} | S;S | \text{if } \varphi \text{ then } S \text{ else } S | \text{while } \varphi \text{ do } S$
$t ::= c | x | -t | t + t| t \cdot t\text{ mit } c \in \mathbb Z$
$\varphi ::= \bot | \top | t = t | t < t| t>t| \neg \varphi | \varphi \land \varphi | \varphi \lor \varphi$

### Mehrdeutigkeit

Wie in der Syntax der [Aussagenlogik](Aussagenlogik.md)/[Prädikatenlogik](Logik/Prädikatenlogik.md) lassen sich Klammern und andere Good Coding Practices (Einrueckung, etc. ) verwenden, um die Syntax eines Programms eindeutig zu machen.

### Freie Variablen

Die Menge freier Variablen in einem Programm $P$, die als $FV(P)$ bezeichnet wird, sind Variablen, die in $P$ vorkommen, ausschließlich der lokalen Variablen.




