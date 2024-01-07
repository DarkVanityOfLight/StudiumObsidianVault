
> Marcel Wirdel, Kilian Lichtner

## Aufgabe 1

_1_
Angenommen: 
Die Endlichkeit des Grades ist anhand der Formel $\varphi$ beschreibbar.
Sei $\sigma' = \lbrace E_{/2}, a\rbrace$.
Sei $\lambda_k$ die folgende $\sigma'$-Formel
$$\begin{align}
\exists x_1, \dots x_k (((E(x_1, a) \land (x_1 \not = a)) \land (E(x_2, a) \land (x_2 \not = a))\dots \land (E(x_k, a) \land (x_k \not = a))\\
\land (a \not =  x_1) \land (a\not= x_2) \land \dots \land (a\not= x_k))
\end{align}$$
Also der Knoten $a$ hat den Grad grösser gleich $k$.

Wir definieren die Theorie
$$T:= \lbrace \varphi \rbrace \cup \lbrace \lambda_k : k\ge 1\rbrace$$
Jede endliche Teilmenge von $T$ enthält nur endlich viele Sätze der Art $\lambda_k$, d.h. sie hat ein endliches Modell. Nach dem Kompaktheitssatz hat $T$ ein unendliches Modell, was ein Widerspruch zu $\varphi$ ist.

_2_
Da die Eigenschaft nicht ausdrückbar ist, gibt es keine Prädikaten-logische Formel $\varphi$ die überprüft ob ein Geschenk unendlich viele weite Geschenke "angeheftet" hat. 


## Aufgabe 2
_1_
$$\begin{align}
A1:= \\
&\exists z \forall x \forall y \Bigl[\bigl(P(y)\to Q(x,x)\bigr) \land \bigl(Q(x,y)\to R(y)\bigr) \land P(z) \land \bigl(\neg R(z)\lor \neg P(z)\bigr)\Bigr]\\
\iff&\exists z \forall x \forall y \Bigl[\bigl(\neg P(y) \lor Q(x,x)\bigr) \land \bigl(\neg Q(x,y) \lor R(y)\bigr) \land P(z) \land \bigl(\neg R(z)\lor \neg P(z)\bigr)\Bigr]
\end{align}$$

Wir führen das Funktionssymbol $c_{/0}$ ein und erhalten folgende erfüllbarkeits äquivalente Formel in SKNF:
$$\begin{align}
A2 := \forall x \forall y \Bigl[\bigl(\neg P(y) \lor Q(x,x)\bigr) \land \bigl(\neg Q(x,y) \lor R(y)\bigr) \land P(c) \land \bigl(\neg R(c)\lor \neg P(c)\bigr)\Bigr]
\end{align}$$

$$\Sigma = \lbrace(\neg P(y) \lor Q(x,x)), (\neg Q(x,y) \lor R(y)), P(z), (\neg R(c)\lor \neg P(c))\rbrace$$

![](resfo1.excalidraw.md)

_2_
$$\begin{align}A1:=& \\
&\neg \Biggl( \bigl( \forall y Q(y) \bigr) \lor \neg \Biggl( \forall x\Biggl[ \bigl(Q(x) \lor R(x) \bigr) \land \biggl(\exists z \Bigl[ \neg P(z) \land \bigl(P(z) \lor \neg R(x) \bigr) \Bigr] \biggr) \Biggr] \Biggr) \Biggr)\\
\iff&\neg \Biggl( \bigl( \forall y Q(y) \bigr) \lor \neg \Biggl( \forall x \exists z\Biggl[ \bigl(Q(x) \lor R(x) \bigr) \land \biggl( \neg P(z) \land \bigl(P(z) \lor \neg R(x) \bigr)  \biggr) \Biggr] \Biggr) \Biggr)\\
\iff&\neg \Biggl( \forall x \exists z\bigl( \forall y Q(y) \bigr) \lor \neg \Biggl( \bigl(Q(x) \lor R(x) \bigr) \land \biggl( \neg P(z) \land \bigl(P(z) \lor \neg R(x) \bigr)  \biggr) \Biggr) \Biggr)\\
\iff&\neg \Biggl( \forall y\forall x \exists z \bigl(Q(y) \bigr) \lor \neg \Biggl( \bigl(Q(x) \lor R(x) \bigr) \land \biggl( \neg P(z) \land \bigl(P(z) \lor \neg R(x) \bigr)  \biggr) \Biggr) \Biggr)\\
\iff&\neg \forall y\forall x \exists z  \Biggl(   \bigl(Q(y) \bigr) \lor \neg \Biggl( \bigl(Q(x) \lor R(x) \bigr) \land \biggl( \neg P(z) \land \bigl(P(z) \lor \neg R(x) \bigr)  \biggr) \Biggr) \Biggr)\\
\iff& \exists y \neg\forall x \exists z \Biggl(   \bigl(Q(y) \bigr) \lor \neg \Biggl( \bigl(Q(x) \lor R(x) \bigr) \land \biggl( \neg P(z) \land \bigl(P(z) \lor \neg R(x) \bigr)  \biggr) \Biggr) \Biggr)\\
\iff& \exists y \exists x \neg\exists z \Biggl(   \bigl(Q(y) \bigr) \lor \neg \Biggl( \bigl(Q(x) \lor R(x) \bigr) \land \biggl( \neg P(z) \land \bigl(P(z) \lor \neg R(x) \bigr)  \biggr) \Biggr) \Biggr)\\
\iff& \exists y \exists x \forall z \neg\Biggl(   \bigl(Q(y) \bigr) \lor \neg \Biggl( \bigl(Q(x) \lor R(x) \bigr) \land \biggl( \neg P(z) \land \bigl(P(z) \lor \neg R(x) \bigr)  \biggr) \Biggr) \Biggr)\\
\iff& \exists y \exists x \forall z \Biggl(\neg\bigl(Q(y) \bigr) \land \neg\neg \Biggl( \bigl(Q(x) \lor R(x) \bigr) \land \biggl( \neg P(z) \land \bigl(P(z) \lor \neg R(x) \bigr)  \biggr) \Biggr) \Biggr)\\
\iff& \exists y \exists x \forall z\Biggl(\neg Q(y) \land\Biggl( \bigl(Q(x) \lor R(x) \bigr) \land \biggl( \neg P(z) \land \bigl(P(z) \lor \neg R(x) \bigr)  \biggr) \Biggr) \Biggr)\\
\end{align}$$
Wir verwenden die Tseitsin Transformation um die Formel in KNF umzuwandeln:
$$
\varphi = \Biggl(\neg Q(y) \land\Biggl( \bigl(Q(x) \lor R(x) \bigr) \land \biggl( \neg P(z) \land \bigl(P(z) \lor \neg R(x) \bigr)  \biggr) \Biggr) \Biggr)
$$
$C = \emptyset$

$$
\varphi_1 = \Biggl(\neg Q(y) \land\Biggl( \bigl(Q(x) \lor R(x) \bigr) \land \biggl( \neg P(z) \land X_1 \biggr) \Biggr) \Biggr)
$$
$C = \lbrace  (\neg X_1 \lor P(z) \lor \neg R(x)), (\neg P(z) \lor X_1), (R(x) \lor X_1)) \rbrace$ 

$$
\varphi_2 = \Biggl(\neg Q(y) \land\Biggl( X_2 \land \biggl( \neg P(z) \land X_1 \biggr) \Biggr) \Biggr)
$$
$C = \lbrace  (\neg X_1 \lor P(z) \lor \neg R(x)), (\neg P(z) \lor X_1), (R(x) \lor X_1)) \rbrace \cup \lbrace (\neg X_2 \lor Q(x) \lor R(x)), (\neg Q(x) \lor X_2), (\neg R(x) \lor X_2) \rbrace$
Nach Anwendung der Klammer regeln erhalten wir:
$$
\varphi_2 = \neg Q(y) \land X_2 \land \neg P(z) \land X_1 
$$
In KNF, nun hängen wir noch die Menge $C$ an.

$$\begin{align}
\varphi_3 :=& \neg Q(y) \land X_2 \land \neg P(z) \land X_1 \land \\
&(\neg X_1 \lor P(z) \lor \neg R(x)) \land (\neg P(z) \lor X_1) \land (R(x) \lor X_1))  \land\\
& (\neg X_2 \lor Q(x) \lor R(x)) \land (\neg Q(x) \lor X_2)\land (\neg R(x) \lor X_2)
\end{align}$$

Mit den Quantoren: 
$$\begin{align}A2 :=&\exists y \exists x \forall z\\
& \neg Q(y) \land X_2 \land \neg P(z) \land X_1 \land \\
&(\neg X_1 \lor P(z) \lor \neg R(x)) \land (\neg P(z) \lor X_1) \land (R(x) \lor X_1))  \land\\
& (\neg X_2 \lor Q(x) \lor R(x)) \land (\neg Q(x) \lor X_2)\land (\neg R(x) \lor X_2)
\end{align}$$

Und in PNF:
$$\begin{align}
A3 := &\forall z\\
& \neg Q(c_1) \land X_2 \land \neg P(z) \land X_1 \land \\
&(\neg X_1 \lor P(z) \lor \neg R(c_2)) \land (\neg P(z) \lor X_1) \land (R(c_2) \lor X_1))  \land\\
& (\neg X_2 \lor Q(c_1) \lor R(c_2)) \land (\neg Q(c_2) \lor X_2)\land (\neg R(c_2) \lor X_2)
\end{align}$$


![](resofo2.excalidraw.md)

## Aufgabe 3
$$\forall x (C_1(x) \land C_1(f(x))$$
Da wir in jedem Schritt der Resolution neue Terme erhalten, ändert sich unsere Menge $S$ immer, da wir aber auch niemals die leere Menge herleiten können wird der Algorithmus niemals terminieren.


## Aufgabe 4

Wir weisen jeder Funktion, jeder Konstante und jeder Operation der Aussagenlogik eine eindeutige Zahl zu, da das Vokabular abzählbar ist funktioniert dies in den natürlichen Zahlen. 


Um nun eine Formel zu encodieren, traversieren wir den Baum der Formel mithilfe der Tiefensuche.
Wir starten mit $N=1$ und der Primzahl $P = 2$
Bei jedem "entdeckten" Operator nehmen wir die nächste Primzahl und rechnen $N = N \cdot P^o$ wobei $o$ die Zahl des Operators ist. Wir führen quasi eine Primzahl Zerlegung "rückwärts" durch und gehen damit sicher das jeder Grundterm seine eigene eindeutige Zahl hat.

Da eine Herbrand Struktur aus allen Grundtermen besteht, und alle Grundterme wie oben gezeigt durch eine eindeutige Natürliche Zahl dargestellt werden können, und diese eben Abzählbar sind ist auch die Herbrand Struktur abzählbar.