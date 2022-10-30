Sequenzen, endliche Folgen von Elementen, lassen sich mit Hilfe [endlicher Abbildungen](Endliche%20Abbildungen.md) modellieren.

## Beispiel
> Anja Florian Lisa Ralf

Die Elemente werden von links nach rechts beginnend mit $0$ durchnummeriert.
>{$0 \mapsto$ Anja, $1 \mapsto$ Florian, $2 \mapsto Lisa$, $3 \mapsto$ Ralf}

---

## Notation
Eine Sequenz s von Elementen aus $A$ ist eine [endliche Abbildungen](Endliche%20Abbildungen.md) des Typs $\mathbb N \mapsto_{fin} A$ mit $dom s = \mathbb N_n$
$\mathbb N_n := \{0, ..., n-1\}$ ist ein Anfangsabschnitt der natürlichen Zahlen
Die Menge aller Sequenzen über $A$ notieren wir mit $A^*$.
Ist $dom s = \mathbb N_n$, dann heißt $n$ die Länge von $s$ notiert $len s:=n$.

---
## Konstruktion und Manipulation
Um Sequenzen zu konstruieren bzw. zu manipulieren, verwenden wir die folgenden Operationen:

### Leere Sequenz
Die leere Sequenz $\epsilon$ mit $dom \epsilon := \mathbb N_0$

### Einelementige Sequenz
Ist $a \in A$, dann verwenden wir oft das Element $a$ selbst als Abkürzung für die einelementige Sequenz $\{0 \mapsto a\}$
### Konkatenation
Die Konkatenation von $s_1$ und $s_2$ notiert $s_1 \cdot s_2$ mit 
$dom (s_1 \cdot s_2):= dom s_1 \cup \{i + len s_1 | i \in dom s_2\}$ und 
$$
    (s_1 \cdot s_2)(i) := 
    \left\{\begin{align}
    &s_1(i) &&falls\ i \in dom\ s_1&\\
    &s_2(i -len\ s_2) &&sonst
    \end{align}\right.
$$
### Die n-fache Wiederholung
Die n-fache Wiederholung von $s$ notiert $s^n$ mit $s^0 := \epsilon$ und $s \cdot s^n =: s^{n+1} := s^n \cdot s$ 