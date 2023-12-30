
> Marcel Wirdel, Kilian Lichtner
## Aufgabe 1

_1_
__CPF__
$$\begin{align}
A_1=& \forall x. \forall y. \Bigl(x<y \to \bigl(\exists z. (x<z \land z<y)\bigr)\Bigr)\\
\iff& \forall x. \forall y. \Bigl(\neg(x<y) \lor \bigl(\exists z. (x<z \land z<y)\bigr)\Bigr)\\
\iff& \forall x. \forall y. \exists z. \Bigl(\neg(x<y) \lor \bigl( (x<z \land z<y)\bigr)\Bigr)
\end{align}$$

__SNF__

$$\begin{align}
A_1 =&\forall x. \forall y. \exists z. \Bigl(\neg(x<y) \lor \bigl( (x<z \land z<y)\bigr)\Bigr)\\
\iff& \forall x. \forall y. \Bigl(\neg(x<y) \lor \bigl( (x<f(x, y) \land f(x, y)<y)\bigr)\Bigr)
\end{align}$$

_2_

$$\mathfrak S = \left( \mathbb R, \lbrace </2,\; f/2\rbrace, \left\lbrace <_\mathbb R, f^2(x, y) \to x+y\right\rbrace \right)$$

_3_

$$\mathfrak S = \left(\mathbb R, \lbrace </2, f/2\rbrace, \left\lbrace <_\mathbb R, f^2(x, y) \to \frac{(x+y)}{2} \right\rbrace\right)$$


---

_1_

__CPF__
$$
A_2=\forall x_1. \exists x_2. \forall x_3. \exists x_4. p(x_1,x_2,x_3,x_4)
$$ 
__SNF__
$$\begin{align}
\iff&\forall x_1. \forall x_3. \exists x_4. p(x_1,f(x_1),x_3,x_4)\\
\iff&\forall x_1. \forall x_3 p(x_1,f(x_1),x_3, g(x_1, x_3))\\
\end{align}$$

---

__CPF__
$$\begin{align}
A_3=&\bigl(\forall x. p(x) \bigr) \lor \bigl(\forall x. \exists y. q(x,y) \bigr)\\
\iff&\bigl(\forall x. p(x) \bigr) \lor \bigl(\forall z. \exists y. q(z,y) \bigr)\\
\iff&\forall x. \forall z. \exists y.\bigl( p(x)  \lor  q(z,y) \bigr)\\
\end{align}$$

__SNF__

$$\begin{align}
A_3 =& \forall x. \forall z. \exists y.\bigl( p(x)  \lor  q(z,y) \bigr)\\
\iff&\forall x. \forall z.\bigl( p(x)  \lor  q(z,f(x, z)) \bigr)
\end{align}$$

___


_1_

__CPF__
$$\begin{align}
A_4=&\forall y. \Biggl[\bigl(\forall x. p(x,y) \bigr) \to \biggl(\forall x. \Bigl[p(y,x) \land \bigr(\exists y. q(y) \bigr)\Bigr]\biggr)\Biggr]\\
\iff &\forall y. \Biggl[\neg\bigl(\forall x. p(x,y) \bigr) \lor \biggl(\forall x. \Bigl[p(y,x) \land \bigr(\exists y. q(y) \bigr)\Bigr]\biggr)\Biggr]\\
\iff &\forall y. \Biggl[\bigl(\exists x. \neg p(x,y) \bigr) \lor \biggl(\forall x. \Bigl[p(y,x) \land \bigr(\exists y. q(y) \bigr)\Bigr]\biggr)\Biggr]\\
\iff &\forall y. \Biggl[\bigl(\exists x. \neg p(x,y) \bigr) \lor \biggl(\forall z. \Bigl[p(y,z) \land \bigr(\exists a. q(a) \bigr)\Bigr]\biggr)\Biggr]\\
\iff &\forall y. \exists x.\Biggl[\bigl( \neg p(x,y) \bigr) \lor \biggl(\forall z.\exists a.\Bigl[p(y,z) \land \bigr( q(a) \bigr)\Bigr]\biggr)\Biggr]\\
\iff &\forall y. \exists x.\forall z.\exists a.\Biggl[\bigl( \neg p(x,y) \bigr) \lor \biggl(\Bigl[p(y,z) \land \bigr( q(a) \bigr)\Bigr]\biggr)\Biggr]\\
\end{align}$$



__SNF__

$$\begin{align}
A_4 =& \forall y. \exists x.\forall z.\exists a.\Biggl[\bigl( \neg p(x,y) \bigr) \lor \biggl(\Bigl[p(y,z) \land \bigr( q(a) \bigr)\Bigr]\biggr)\Biggr]\\
\iff& \forall y.\forall z.\Biggl[\bigl( \neg p(f(y),y) \bigr) \lor \biggl(\Bigl[p(y,z) \land \bigr( q(g(y, z)) \bigr)\Bigr]\biggr)\Biggr]\\
\end{align}$$


## Aufgabe 2

Nehmen wir an für eine Beliebige Struktur $(\mathfrak S, v)$:
$$(\mathfrak S, v) \vDash (\exists x. A) \lor (\exists x. B)$$

Es gibt also ein Element $d$ für das entweder $(\mathfrak S, v) \vDash A[d/x]$ oder $(\mathfrak S, v) \vDash B[d/x]$.
Nehmen wir an der erste Fall hält, (der zweite ist gleich). 
Da $(\mathfrak S, v) \vDash A[d/x]$ gilt, wissen wir das auch $(\mathfrak S, v)\vDash (A\lor B)[d/x]$  gilt, da:
$$\begin{align}
&(\mathfrak S, v)\vDash (A\lor B)[d/x]\\
&(\mathfrak S, v)\vDash (A[d/x]\lor B[d/x])
\end{align}$$
und wir bereits wissen das $(\mathfrak S, v) \vDash A[d/x]$ hält. Dies gilt für jede beliebige Struktur $(\mathfrak S, v)$, und daher gilt
$$(\exists x. A) \lor (\exists x. B) \vDash \exists x. (A\lor B)$$


## Aufgabe 3

Wir interpretieren unser Universum als die Knoten eines Graphen, der Graph hat unendlich abzählbare Knoten, wir nummerieren die Knoten in $\mathbb N$. Die Relation $P$ interpretieren wir als das existieren einer Gerichteten Kante $P: \mathbb N \times \mathbb N \mapsto \lbrace\top, \bot\rbrace$.

Nun konstruieren wir unseren Graphen:
- Für jeden Knoten $n$, erstellen wir eine Kante zu jedem anderen Knoten identifiziert durch eine Zahl $m$ sodass $m > n$ .

Anders beschrieben als Adjazensliste:
$$\begin{align}
&1: 2, 3, 4\dots\
&2: 3, 4, 5\dots\\
&3: 4, 5, 6\dots\\
&\dots\\
\end{align}$$
![](infgraphsfin.excalidraw.md)

Mit dem Kompaktheitssatz können wir nun zeigen das dieser Graph den Formelsatz erfüllt: 
Dafür wählen wir ein beliebiges aber festes $n$ was den letzten Knoten in unserem Graphen beschreibt.
Nach unserer Konstruktion hat jeder Knoten eine Kante zu jedem Nachfolger bis $n$, $n$ hat nur eingehende Kanten. Daher gilt das jeder Knoten entweder eine eingehende oder eine Ausgehende Kante zu jedem anderen hat. Formel $1$ ist also erfüllt.
Da wir keine Zyklen oder "rückwärts-gerichtet" Kanten haben folgt Formel $2$ aus dem selben Grund wie Formel 1, ein Knoten ist immer genau mit allen seinen Nachfolgern verbunden. Formel $3$ ist nach unserer Konstruktion Trivial erfüllt, es gibt keine Selbstreferenzen in den Kanten.
Der erste Knoten in unserer Konstruktion erfüllt die $4$ Formel, er hat eine ausgehende Kante zu jedem anderen Knoten. Der letzte Knoten $n$ erfüllt die letzte Bedingung, er ist grösser als jeder andere Knoten und hat daher eine eingehende Kante von jedem anderem.

Die gilt für jedes $n$, da $\mathbb N$ abzählbar ist könne wir jede Teilmenge aufzählen, aus dem Kompaktheitssatz folgt nun das die Konstruktion auch für eine unendliche Struktur gilt.

## Aufgabe 4

_1_
Gegeben sei eine FO-Formel $\varphi$, eine endliche Menge von Elementen$U$, eine Menge von Relation/Funktionssymbolen und ihre Interpretation $F$, sowie eine Menge von Variablen $v$.

Um den Wahrheitswert der Formel $\varphi$zu prüfen:

1. **Substitution der freien Variablen:**
   - Ersetze alle freien Variablen in der Formel $\varphi$ durch die gegebene Valuation $v$.
   - Werte Funktionen/Relationssymbole aus, die nun keine Variablen mehr enthalten.

2. **Rekursion über die Formel:**
   - Überprüfe, ob es Funktionen/Relationssymbole gibt, die keine Variable mehr enthalten. Wenn ja, werte diese aus.

3. **Behandlung von Quantoren:**
   - Wenn ein Allquantor ($\forall$) auftritt:
     - Iteriere durch alle Elemente $u$ in $U$.
     - Evaluiere die Subformel ohne den Allquantor $\phi$ und ersetze die gebundene Variable in $phi$ durch $u$.
     - Sei $x$ die durch den Quantor gebundene Variable. Evaluiere $\phi_{[u/x]}$.
     - Wenn $\phi$ für alle $u$ zu wahr auswertet, ist $\varphi$ wahr.

   - Wenn ein Existenzquantor ($\exists$) auftritt:
     - Iteriere durch alle Elemente $u$ in $U$.
     - Evaluiere die Subformel ohne den Existenzquantor $phi$ und ersetze die von dem Quantor gebundene Variable $x$ durch $u$: $phi_{[u/x]}$.
     - Wenn eine dieser Evaluationen von $\phi$ zu wahr auswertet, ist die Formel $\varphi$ wahr.

_2_

Da $A$ erfüllbar ist gibt es ein Modell $M$ sodass $A$ gilt.
Wir konstruieren dieses Modell wie Folgt:
Für jeden Existenzquantoren $\exists x_i$ in  $A$ wählen wir ein Element $a_i$ aus unsere Domain sodass die Formel zu wahr auswertet.
Wir erweitern unser Modell $M$ um das Element $a_i$. In der Formel $B$ müssen mindestens $n$ gebundene Variablen auftreten, wir wählen maximal $n$ Elemente für $n$ Existenzquantoren. Daraus folgt $|M| \leq |B|$.

$M$ ist ein Modell für $A$, da wir für jeden Existenz Quantoren genau ein Element in unserem Modell haben, das die Formel erfüllt. $B$ enthält keine Quantoren, daraus folgt das $B$ in $M$  gilt.

_3_

Wir wählen unsere Domain, sodass alle Elemente die wir aus $2$ benötigen sowie alle Konstanten darin enthalten sind. Da $|M| \leq |B|$ sind dies endlich viele. Nun evaluieren wir die Formel mit $1$, gibt der Algorithmus wahr aus ist die Formel erfüllbar, sonst nicht.