
> Marcel Wirdel, Kilian Lichtner

## Aufgabe 2

__1)__

$$\begin{align}
&B_1 = (\neg A \to \neg B) \to (B\to A)\\
&B_2 = ((\neg A \to \neg B) \to (B\to A)) \to (((\neg A \to \neg B) \to B) \to ((\neg A \to \neg B)\to A))\\
&B_3 = ((\neg A \to \neg B) \to B) \to ((\neg A \to \neg B) \to A)
\end{align}$$

$B_1$ verwendet  Axiom $3$.
$B_2$ verwendet das zweite Axiom unseres Deduktions Systems 
$$(A\to (B\to C)) \to ((A\to B) \to (A \to C))$$

$B_3$ verwendet den Modus Ponens, $B_1$ ist angenommen daher gilt die rechte Seite der Implikation:
$$((\neg A\to\neg B)\to B)\to((\neg A\to\neg B)\to A))$$

__2)__

$$\begin{align}
&\mathcal F_0 \vdash (A\to B) \to \left((B \to C) \to (A\to C)\right)\\
&\mathcal F_0, (A\to B) \vdash (B\to C) \to (A\to C)\\
&\mathcal F_0, (B \to C) \vdash A\to C\\
&\mathcal F_0, A \vdash C\\
&C&|MP(A, A\to C)
\end{align}$$


__3)__

$$\begin{align}
&\mathcal F_0 \vdash B \to \neg \neg B\\
&\mathcal F_0 \vdash \neg\neg(B \to \neg \neg B) \to (B\to \neg \neg B)\\
&MP (\neg\neg (B \to \neg \neg B),\neg\neg(B \to \neg \neg B) \to (B\to \neg \neg B))
\end{align}$$

__4)__

$$\begin{align}
&\mathcal F_0 \vdash (A\to B) \to ((A\to \neg B) \to (A\to C))\\
&\mathcal F_0, (A\to B) \vdash (A \to \neg B) \to (A\to C)\\
&\mathcal F_0, (A\to \neg B) \vdash A \to C\\
&\mathcal F_0, A \vdash C\\
&C &|MP(A, A \to C)
\end{align}$$




## Aufgabe 3

$$A_1 \equiv \forall z.(z = x \to (\forall x. z=x))$$


_Bound_
$z$
$x$ in der inneren Formel $\forall x.z=x$

_Free_
$x$ im Teil der Formel $z = x$

Die Formel ist kein Satz da die Variable $x$ teilweise Frei ist.

$$\begin{align}
&val_{\mathfrak S, \mathfrak v}(\forall z.(z = x \to (\forall x. z=x)))\\
\iff& \forall z.(z = val(x) \to (\forall x.z = x))\\
\iff& \forall z.(z = 1 \to (\forall x.z = x))
\end{align}$$

Die Aussage ist Falsch, für die Belegung $z=1$, und das innere $x=0$
$$
(1 = 1) \to (1 = 0)
$$


---

$$A_2 \equiv \exists n.\forall x.(x+n = x)$$
_Bound_
$n, x$

_Free_

Die Formel ist ein Satz

Die Aussage ist wahr, da $n = 0$ nach der Definition von $I(n+x)$ für ein Beliebiges $x$, $x$ ergibt.

---

$$A_3 \equiv \forall x.\exists y.x\cdot y \not= x$$

_Bound_
$x, y$

_Free_

Die Formel ist ein Satz

Die Aussage ist wahr.

---

$$A_4 \equiv \exists z.\forall x .\left( x\not=z \to (\exists y.x \cdot y \not = x) \right)$$

_Bound_
$z, x, y$

_Free_

Die Formel ist ein Satz

Die Aussage ist wahr und folgt aus Aussage $A_3$.

---

$$A_5 \equiv \exists x. \forall y. even(x+y)$$

_Bound_
$x, y$

_Free_

Die Formel ist ein Satz

Die Aussage ist wahr da ein Additives Inverses Existiert. 

---