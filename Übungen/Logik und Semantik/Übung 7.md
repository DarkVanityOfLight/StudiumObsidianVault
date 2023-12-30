
> Marcel Wirdel, Kilian Lichtner


## Aufgabe 2

$$E_1 = P(a, x, f(g(y)))$$
$$E_2 = P(y, f(z), f(z))$$

$$\theta = \lbrace a/y, f(z)/x, g(a)/z\rbrace$$

$$E_1\theta = P(a, f(g(a)), f(g(a)))$$
$$E_2\theta = P(a, f(g(a)), f(g(a)))$$

---

$$E_1 = P(x, g(f(a)), f(x))$$
$$E_2 = P(f(a), y, y)$$

Nicht unifizierbar.


---

$$E_1 = P(x, g(f(a)), f(x))$$
$$E_2 = P(f(y), z, y)$$

Nicht unifizierbar.

---

$$E_1 = P(a, x, f(g(y)))$$
$$E_2 = P(z, h(z, u), f(u))$$

$$\theta = \lbrace a/z, h(z, u)/x, g(y)/u\rbrace$$

$$E_1\theta = P(a, h(a, g(y)), f(g(y)))$$
$$E_2\theta = P(a, h(a, g(y)), f(g(y)))$$


## Aufgabe 3

$$\begin{align}
&\vDash \phi = \forall x(A(x, f(x))) \to \forall x\exists y(A(x, y))\\
\iff&\not\vDash \neg\phi\\
\iff&\not\vDash \neg(\forall x(A(x, f(x))) \to \forall x\exists y(A(x, y)))\\
\iff&\not\vDash \neg(\neg \forall x(A(x, f(x))) \lor \forall x\exists y(A(x, y))\\
\iff&\not\vDash \forall x(A(x, f(x))) \land \neg\forall x\exists y(A(x, y))\\
\iff&\not\vDash \forall x(A(x, f(x))) \land \exists x\neg\exists y(A(x, y))\\
\iff&\not\vDash \forall x(A(x, f(x))) \land \exists x\neg\exists y(A(x, y))\\
\iff&\not\vDash \forall x(A(x, f(x))) \land \exists x\forall y \neg(A(x, y))\\
\iff&\not\vDash \forall x(A(x, f(x))) \land \exists z\forall y \neg(A(z, y))\\
\iff&\not\vDash \exists z\forall y\forall x (A(x, f(x)) \land  \neg(A(z, y)))
\end{align}$$

$$\not\vDash \phi \iff \not \vDash \varphi$$
$$\varphi = \forall y\forall x (A(x, f(x)) \land  \neg(A(c, y)))$$

Der Quantoren freie teil ist bereits in CNF

Nach dem Ground Resolution Theorem:

![](GroundResolution.excalidraw.md)

Daher ist $\not \vDash \varphi$ unerfüllbar, da $\not\vDash \phi \iff \not \vDash \varphi$, gilt demnach $\not\vDash \neg\phi$ ist unerfüllbar und damit gilt $\vDash \phi$.


## Aufgabe 4
_1_

$$
Eq = (\forall a\forall b(E(a, b) \to E(b, a))) \land (\forall a (E(a, a)))\land (\forall a\forall b\forall c (E(a, b) \land E(b, c) \to E(a, c)))
$$

_2_

$$K = (\forall a, b(E(a, b) \to (P(a) \leftrightarrow P(b)))) \land \forall a, b(E(a, b) \to E(f(a), f(b)))$$
_3_

Zuerst hängen wir die beiden Sätze $Eq$ und $K$  an $A$
$$A' := A \land Eq \land K$$
Nun ersetzen wir  alle $=$ Relationen in $A$ durch $E$.

Da $Eq$ und $K$ Sätze sind werden keine neuen Variablen eingeführt, unser Modell $M'$ muss nur um eine Relation $E_{/2}$ erweitert werden. Da die Gleichheit genau die Eigenschaften $K$ und $Eq$ erfüllt, ist jedes Modell $M$ von $A$ erweitert mit der Relation genau das Modell $M'$ von $A$.


## Aufgabe 5

_1_

Nehmen wir an $A$ hat ein Herbrand Modell $\mathcal H = \lbrace a_{/0}, P_{/1}, Q_{/2} \rbrace$:

$$\begin{align}
A = P(a) \land \forall x \bigl( P(x) \to (\exists y Q(x, y)) \bigr) \land (\exists x\neg Q(x, a))\\
\end{align}$$
unter unserem Modell:

$$P(a) \land \forall x \bigl( P(x) \to (\exists y Q(x, y)) \bigr) \land (\exists x\neg Q(x, a))$$
Da es nur einen möglichen Wert für in unserem Modell gibt:
$$A = P(a) \land  \bigl( P(a) \to (Q(a, a)) \bigr) \land (\neg Q(a, a))$$
Damit die Formel erfüllbar ist muss $P(c)$ gelten:
$$\begin{align} 
A =& \top \land  \bigl( \top \to (Q(a, a)) \bigr) \land (\neg Q(a, a))\\
\iff& Q(a, a) \land \neg Q(a, a)
\end{align}$$
was nicht gelten kann.

_2_

__CPF__
$$
\begin{align*}
A = & \bigl( P(a) \land \forall x \bigl( P(x) \to (\exists y Q(x, y)) \bigr) \land (\exists x \neg Q(x, a)) \bigr) \\
\iff & \bigl( P(a) \land \forall x \bigl( P(x) \to (\exists y Q(x, y)) \bigr) \land (\exists z \neg Q(z, a)) \bigr) \\
\iff & \bigl( P(a) \land \forall x \exists y \bigl( P(x) \to Q(x, y) \bigr) \land (\exists z \neg Q(z, a)) \bigr) \\
\iff & \forall x \exists y \bigl( P(a) \land ( P(x) \to Q(x, y) ) \land (\exists z \neg Q(z, a)) \bigr) \\
\iff & \exists z \forall x \exists y \bigl( P(a) \land ( P(x) \to Q(x, y) ) \land \neg Q(z, a) \bigr) \\
\end{align*}
$$

__SNF__

$$\begin{align}
A' = \forall x \bigl( P(a) \land ( P(x) \to Q(x, f(y)) ) \land \neg Q(b, a) \bigr)
\end{align}$$

für eine neue Konstante $b$ und ein Funktionssymbol $f_{/1}$

_3_

$$\sigma' = \lbrace a_{/0}, b_{/0}, f_{/1}, P_{/1}, Q_{/2} \rbrace$$

_4_

$$\begin{align}\mathcal H =&\lbrace a, b, f(a), f(b), f(f(a)), f(f(a)), \dots,\\
&P(a), P(f(a)), P(b), P(f(b)), \dots,Q(a, a), Q(b, b), Q(a, b),\dots\rbrace\end{align}$$


