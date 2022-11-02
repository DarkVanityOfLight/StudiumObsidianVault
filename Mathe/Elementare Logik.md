[Aussagen](Aussagen.md), [Mengen](Mengen.md), [[Folgerungen]]
```bash
if x > 1 then
...
fi;
```

![Aussage](Aussagen.md#Aussage)

### Beispiel
$1+2=3$
$1+2=4$
Jede gerade Zahl $>2$ ist die Summe von zwei Primzahlen([Goldbachsche Vermutung](Goldbachsche%20Vermutung.md)).

---
$x>1$ ist keine Aussage solange $x$ nicht festgelegt ist

![Definition](Mengen.md#Definition)

---
## Bemerkung
Objekte = mathematische Objekte
Zusammenfassung = neues Objekt
Wohl unterschieden: Man kann entscheiden ob $a,b \in M$ gleich sind $(a=b)$ oder nicht $(a \not = b)$

---
## Beispiele
$\{0, 1, 2,..., 9\}$ 
$\mathbb N = \{1,2,3,...\}$ $\mathbb N_0 = \{0, 1, 2,...\}$
$\mathbb Z =\{0, 1, -1, 2, -2, ...\}$

---
## Aussageform
> Eine Aussageform auf einer Menge $M$ ist eine Zuordnung einer Aussage $A(x)$ zu jedem Element $x\in M$.

### Unerfüllbar
> Eine Aussageform die wahr ist heißt unerfüllbar.

### Tautologie
> Eine Tautologie ist immer wahr.

### Beispiele
Für $x\in \mathbb Z$ ist $x^2 < 0$ (unerfüllbar)
$x^2 > 0$ (erfüllbar wahr für $x\not = 0$, falsch für $x=0$)
$x^2 \geq 0$ Tautologie

```bash
if (x > 1) then
    if x * x > 1 then
        ...
    fi
fi
```
Aus $x > 1$ folgt $x^2 > 1$ (logische Schlussfolgerung)

Für alle $x \in \mathbb Z$ gilt:
Aus $x>1$ wahr folgt $x^2>1$ wahr.

Es existiert ein $x \in \mathbb Z$ mit $x<0$.
![Quantoren](Quantoren.md)

---


Prädikatenlogik
Aussagen die mit Hilfe von ∀,∃ und Aussageformen formuliert werden können nennt man Aussagen der Prädikatenlogik.

Sätze und Beweise
Eine wahre Aussage der Prädikatenlogik bezeichnet man als Satz, ihre Herleitung beizeichnen wir als Beweis

Lemma: Zwischenergebnis
Proposition: nicht so zentrales Ergebnis
Corollar: Folgerung aus einem Satz

---

## Logische Operationen
Eine logische Operation verknüpft [Aussagen](Aussagen.md) zu einer neuen [Aussage](Aussagen.md). Damit erhalten wir Aussageformen, die wir als Logische Formel bezeichnen.
![Logisches Oder(Disjunktion)](Aussagen.md#Logisches%20Oder(Disjunktion))
|  $A$ | $B$  | $A\lor B$  |
|---|---|---|
|  1 |  1 |  1 |
|  0 |  1 |  1 |
|  1 |  0 |  1 |
| 0  | 0  |  0 |
![Logisches Und(Konjunktion)](Aussagen.md#Logisches%20Und(Konjunktion))
|  $A$ | $B$  | $A\land B$  |
|---|---|---|
|  1 |  1 |  1 |
|  0 |  1 |  0 |
|  1 |  0 |  0 |
| 0  | 0  |  0 |
![Negation](Aussagen.md#Negation)
| $A$  | $\neg A$  |
|---|---|
| 1  | 0  |
| 0  |  1 |
### Beispiel
```bash
if not A then ... fi
if A and B then ... fi
if A or B then ... fi
```

![Implikation](Aussage| A | B | $A \implies B$ | $B \implies A$ | $A \implies B \land B \implies A$ | $A\iff B$ |
|---|---|----------------|----------------|-----------------------------------|-----------|
| 1 | 1 | 1              | 1              | 1                                 | 1         |
| 1 | 0 | 0              | 1              | 0                                 | 0         |
| 0 | 1 | 1              | 0              | 0                                 | 0         |
| 0 | 0 | 1              | 1              | 1                                 | 1         |n.md#Implikation)

| A  | B  |  $A\implies B$ |
|---|---|---|
| 1  | 1  |  1 |
| 0  |  1 |  1 |   
|  1 |  0 |  0 |
|  0 |  0 |  1 |
