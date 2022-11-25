	Jannis Lauterbach, Kilian Lichtner


## Aufgabe 1

### a)
$a \equiv b \ mod \ m$

#### Reflexiv
Fuer alle $a \in \mathbb Z$ und $n \in \mathbb N$
$$\begin{align}
&a \equiv a \mod  n\\
&n|(a-a)\\
&n|0\\
\end{align}$$
Jede zahl teilt Null daher gilt $a \equiv a\ mod\ a$ als Äquivalenzrelation
$\square$

#### Transitiv
Zu zeigen
Fuer alle $a, b, c \in \mathbb Z$ und $n\in \mathbb N$
$$\begin{align}
&a \equiv b \mod n\\
&a\equiv c \mod n \\
&\implies b\equiv c \mod n\\
&\implies n|(b-c)\\
&\implies (b-c) = t\cdot n|t \in \mathbb Z
\end{align}$$


$$\begin{align}
&n|(b-a) \qquad n|(a-c)\\
&\implies b-a = tn \qquad \implies a-c = un&|& t,u \in \mathbb Z\\
&a = un -c\\
&b -a = tn &|& a = un -c\\
&b -(-vn -c) = tn\\
&b + un -c = tn &|&- un\\
&b -c = tn -un\\
&b-c = n\cdot(t-u) &|& (t-u) = v\\
& b-c = n \cdot v\\
\implies & b \equiv z \mod n\\
\square
\end{align}$$

#### Symmetrisch
Zu zeigen:
Fuer alle $a, b \in \mathbb Z$ und $n \in \mathbb N$
$$\begin{align}
a \equiv b \mod n\\
\implies b \equiv a \mod n
\end{align}$$
$$\begin{align}
&a \equiv b \mod n \iff \\
&a -b = t \cdot n &|& \cdot -1\\
\implies & -(a-b) = t\cdot -n\\
\implies &b\equiv a\\
\square
\end{align}$$

### b)
$$\begin{align}
M = \{[a]| \{\forall a, b \in \mathbb Z | a\equiv b \mod 5\}\}
\end{align}$$


## Aufgabe 2
$$\begin{align}
& 11111111111 : 123259 = 914 \ Rest:51815\\
& \underline{0} \\
& 11 \\
& \ \ \underline{0} \\
& 111 \\
& \quad \underline{0} \\
& 1111 \\
& \quad \ \ \underline{0} \\
& 11111 \\
& \qquad \underline{0} \\
& 111111 \\
& \qquad \ \ \underline{0} \\
& 1111111 \\
& \underline{1109331} \\
& \quad \ \ 17801 \\
& \qquad \quad \ \ \underline{0} \\
& \quad \ \ 178011 \\
& \quad \ \ \underline{123259} \\
& \qquad 547521 \\
& \qquad \underline{493036} \\
& \qquad \ \ 544851 \\
& \qquad \ \ \underline{493036} \\
& \qquad \quad 51815\\
\end{align}$$
$$\begin{align}
& 67360232502 : 123259 = 546493 \ Rest:51815 \\
& \underline{0} \\
& 67 \\
& \ \ \underline{0} \\
& 673 \\
& \quad \underline{0} \\
& 6736 \\
& \quad \ \ \underline{0} \\
& 67360 \\
& \qquad \underline{0} \\
& 673602 \\
& \underline{616295} \\
& \ \ 573073 \\
& \ \ \underline{493036} \\
& \quad 800372 \\
& \quad \underline{739554} \\
& \quad \ \ 608185 \\
& \quad \ \ \underline{493036} \\
& \quad \ \ 1151490 \\
& \quad \ \ \underline{1109331} \\
& \qquad \ \  421592 \\
& \qquad \ \ \underline{369777} \\
& \qquad \quad 51815 \\
\end{align}$$


## Aufgabe 3

### a)
#### Reflexiv
Zu zeigen
Fuer alle $(x, y) \in \mathbb R^2$
$$(x,y) \sim (x,y) \implies f(x, y) = f(x, y)$$
Da einem Element aus der Definitionsmenge genau ein Element der Zielmenge zugeordnet ist, bekommen wir bei gleichen Eingabeparametern das gleiche Ergebniss.

#### Transitiv
Zu zeigen
Fuer alle $(x, y),(x_1, y_1), (x_2, y_2) \in \mathbb R^2$
$$\begin{align}
&(x, y) \sim (x_1, y_1), (x, y) \sim(x_2, y_2)\\
\implies &(x_1,y_1) \sim (x_2, y_2)\\
\\
&f(x, y) = f(x_1, y_1)\\
&f(x, y) = f(x_2, y_2)\\
\implies & f(x_1, y_1) =f(x_2, y_2)
\end{align}$$
Da wir ein eindeutig bestimmtes Ergebniss von $(x, y)$ haben und dieses gleich dem Ergebniss von $(x_1, y_1)$ ist, muss da das Ergebniss das gleiche von $(x_2, y_2)$
gelten das alle drei Ergebnisse das selbe sind und demnach $f(x_1, y_1) = (x_2, y_2)$

#### Symmetrie
Zu zeigen
Fuer alle $(x,y), (x_1, y_1) \in \mathbb R^2$
$$
f(x, y) \sim f(x_1, y_1) \implies f(x_1, y_1) = f(x, y)
$$
Da das Ergebniss von $f$ eindeutig bestimmt ist, bleibt das Ergebniss gleich wenn man die Reihenfolge aendert.

### b)
$$\begin{align}
&[(0, 0)] = \{x, y \in \mathbb R | x + y = 0\}\\
&[(1, -1)] = \{x, y \in \mathbb R | x+y = 0\}\\
&[(1, 1)] = \{x, y \in \mathbb R | x+y = 2\}
\end{align}$$
![semicircle](lines.png)

## Aufgabe 4
### a)

#### Reflexiv:

Zu zeigen:
Für alle $(x, y) \in M$
$(x, y)\sim (x, y)$

Da  die Gerade von $(x, y)$ für ein beliebiges $(x, y) \in M$ zu $(0, 0)$ durch den Punkt $(x, y)$ geht ist die Relation reflexiv.

#### Transitiv:

Zu zeigen:
Für alle $(x, y), (x', y'), (a, b) \in M$
$(x, y) \sim (x', y')$ und $(x, y) \sim (a, b) \implies (x', y') \sim (a, b)$

Es existiert eine Gerade die durch $(x, y), (0, 0)$ und $(x', y')$ geht.
Ausserdem existiert eine Gerade die durch $(x, y), (0, 0)$ und $(a, b)$ geht.
Da beide dieser Geraden durch den Punkt $(0, 0)$ gehen und eine Gerade durch zwei Punkte genau bestimmt werden kann, geht die Gerade $(0, 0), (x', y')$ auch durch $(a, b)$.

#### Symmetrisch:
Zu zeigen:
Für alle $(x, y), (x', y') \in M$
$(x, y) \sim (x', y') \implies (x', y') \sim (x, y)$
Da eine Gerade durch zwei Punkte eindeutig bestimmt ist gilt:
Die Gerade durch $(x, y), (x', y')$ ist dieselbe wie $(x', y') (x, y)$ 

### b)
![semicircle](attachments/semicircle.jpg)
Wir wählen als Represäsentanten der Äquivalenzklassen die Punkte die ein Positives $x$ haben und den Abstand $2$ zum $0$ Punkt haben also: $\sqrt{x^2 + y^2} = 2$


## Aufgabe 5
```csharp
let kongurent (a: int) (b: int) (m: int) = (modulo a m) * (if a < - 0 then -2 else 1) = (modulo b  m) * (if b < 0 then -2 else 1)


```