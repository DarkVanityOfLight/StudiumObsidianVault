
## Task 1

### a)
DNF:
$$\begin{align}
&(\neg A \land \neg B \land C) \lor\\
&(\neg A \land B \land C) \lor\\
&(A \land \neg B \land \neg C)\lor\\
&(A\land B \land C)
\end{align}$$
(KNF) geht auch

### b)

$$\begin{align}

\end{align}$$

| $A$ | $B$ | $f$ |
| ---- | ---- | ---- |
| $0$ | $0$ | $1$ |
| $0$ | $1$ | $1$ |
| $1$ | $0$ | $1$ |
| $1$ | $1$ | $0$ |
DNF:
$$\begin{align}
(\neg A \land \neg B) \lor\\
(\neg A \land B) \lor\\
(A \land \neg B)
\end{align}$$
KNF(negiere die Warheitstabell(auch eingabewerte) und lese wie bei der DNF ab):
$$\begin{align}
\neg(A \land B)\\
(\neg A \lor \neg B)
\end{align}$$

## Task 2

### a)
$$(p\lor q\lor \neg r) \land (p\lor \neg q) \land r\land \neg p \land u$$
$u$ ist Pure, setze $u=1$
$$(p\lor q\lor \neg r) \land (p\lor \neg q) \land r\land \neg p \land 1$$
BCP:
![](WS-2021-2022%20Preliminary%202024-01-24%2014.15.39.excalidraw.md)


### b)

$$
(x\lor y\lor z)\land(x\lor y\lor \neg z) \land(x\lor \neg y\lor z\lor r) \land (\neg r \lor x) \land (x\lor \neg z) \land (\neg x \lor \neg z) \land (\neg x\lor \neg y\lor z) \land (\neg x \lor y) \land (x\lor y\lor \neg z)$$
![](WS-2021-2022%20Preliminary%202024-01-24%2014.24.02.excalidraw)

## Task 3

### a)
$$\begin{align}
&(x \to (y \to z)) \vdash (y \to (x\to z))\\
&y, (x \to (y \to z)) \vdash (x\to z)&|\text{Deduktionstheorem}\\
&x, y, (x \to (y \to z)) \vdash z&|\text{Deduktionstheorem}\\
\end{align}$$

A1: $(x \to (y \to z))$
A2: $y$
A3: $x$

$$MP: \frac{x, \qquad (x\to (y\to z))}{ y\to z}$$
A4: $y\to z$
$$MP: \frac{y, \qquad y\to z}{z}$$

A5: $z$

### b)
$$(x\to (y\to z)), y \vdash (x\to z)$$
A1: $(x\to (y\to z))$
A2: $y$
A3:
$$Ax2: (x \to (y \to z)) \to ((x\to y) \to (x\to z))$$
A4: $$MP: \frac{(x\to (y\to z)), \qquad (x \to (y \to z)) \to ((x\to y) \to (x\to z))}{((x\to y) \to (x\to z))}$$
A5:
$$Ax1: y \to (x\to y)$$
A6: $$MP: \frac{y, \qquad y \to (x\to y)}{(x\to y)}$$
A7: $$MP: \frac{(x\to y), \qquad ((x\to y) \to (x\to z))}{ x\to z}$$

## Task 4

$$\begin{align}
\Sigma = \lbrace&
\forall x \forall y\forall z\left((P(x, y) \land P(y, z)) \to P(x, z) \right),\\
&\forall x P(x, x),\\
&\exists x\forall y \left( P(y, x) \right)\\
\rbrace
\end{align}$$

### a)
$$\begin{align}
&\forall x \forall y\forall z\left(\neg(P(x, y) \land P(y, z)) \lor P(x, z) \right)\\
\iff& \forall x \forall y\forall z\left((\neg P(x, y) \lor \neg P(y, z)) \lor P(x, z) \right)
\end{align}$$

$$\forall x P(x, x)$$

$$\begin{align}
\varphi = \exists x\forall y \left( p(y, x) \right)\\
\varphi' = \forall y \left( P(y, c) \right)\\
\end{align}$$

## b)

Es gibt ein unendliches Modell, Interpretieren wir $P$ als grösser gleich $\geq$, über dem Universum der natürlichen Zahlen $\mathbb Q$.
Die Transitivität von $\geq$ erfüllt Formel 1.
Die Reflexivität von $\geq$ erfüllt Formel 2. 
$0$ ist Vorgänger aller Zahlen in $Q$ also gilt $\forall x (x \geq 0)$ 
$\mathbb Q$ ist unendlich also gibt es ein unendliches Modell für $\Sigma$


## Task 5

Nach dem Kompaktheitssatz:

Eine unendliche Menge an Formeln ist genau dann unerfüllbar wenn es eine endliche unerfüllbare Teilmenge gibt.
