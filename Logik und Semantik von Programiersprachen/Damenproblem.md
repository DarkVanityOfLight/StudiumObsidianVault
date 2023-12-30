
Das Damenproblem mithilfe von [Constraintprogrammierung](Constraintprogrammierung.md):

> Constrain 1
> In jeder Reihe/Spalte steht genau eine Dame

> Constrain 2
> Die Damen können einander nicht schlagen.

__Eingabe__ Eine Zahl $n \in \mathbb N$
__Ausgabe__: Eine gültige Lösung zum Damenproblem für die Groesse $n$

Diese Constraints können wir in die [Aussagenlogik](Aussagenlogik.md) übersetzen.


## Constraint 1

In jeder Zeile steht genau eine Dame:

1.a In jeder Zeile steht mindestens eine Dame:
$$\bigwedge^n_{i=1} \bigvee^n_{j=1} p_{i,j}$$
1.b In jeder Zeile steht höchstens eine Dame:
$$\bigwedge^n_{i=1}\bigwedge^n_{j=1} \bigwedge_{1 \leq k \leq n, k\not=j} (p_{i, j} \implies \neg p_{i, k})$$

In jeder Spalte steht genau eine Dame:

1. a In jeder Spalte steht mindestens eine Dame:
$$\bigwedge^n_{j=1}\bigvee^n_{i=1} p_{i, j}$$

1.b In jeder Spalte steht höchstens eine Dame:
$$
\bigwedge^n_{j=1}\bigwedge^n_{i=1}\bigwedge_{1 \leq k \leq n, k\not= i}  (p_{i,j} \implies \neg p_{i, k})
$$

## Constraint 3

In jeder Diagonale steht höchstens eine Dame

Wir unterscheiden zwischen zwei Diagonalarten:

$45\degree$ und $-45\degree$.

1. $45\degree$
Wir beobachten: Andere Felder, die in der gleichen $45\degree$ Diagnonale wie $p_{i,j}$ liegen, sind genau Folgendes


2. $-45\degree$
Wir beobachten: Andere Felder, die in der gleichen $-45\degree$ Diagnonale wie $p_{i,j}$ liegen, sind genau Folgendes:

$$p_{i+k, j+k} \iff 1 \leq i + k, j+k \leq n$$
oder
$$p_{i-k, j-k} \iff 1 \leq i -k, j-k \leq n$$

Daraus erhalten wir:

$$\bigwedge^n_{i=1}\bigwedge^n_{j=1}\bigwedge_{1 \leq i+k, j+k \leq n} (p_{i,j} \implies \neg p(p_{i+k, j+k},))$$

$$\bigwedge^n_{i=1}\bigwedge^n_{j=1}\bigwedge_{1\leq i -k, j-k \leq n} (p_{i,j} \implies \neg p_{i-k, j-k})$$

