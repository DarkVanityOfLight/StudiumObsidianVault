
> Marcel Wirdel, Kilian Lichtner

## Aufgabe 5

> Eine Aussagenlogische Formel $A$ hat die selbe Anzahl an Klammern und Operatoren

__Induktionsanfang__: 

Wir betrachten den Fall mit keinem Operator:
$$A = p_i$$
dann gilt:
$$\begin{align}
k(A) = op(A)\\
k(p_i) = op(p_i)\\
0 = 0
\end{align}$$

__Induktionsvoraussetzung__:

Es gelte für zwei beliebige aber feste Formeln $A, B \in F$:
$$\begin{align}
k(A) = op(A)\\
k(B) = op(B)\\
\end{align}$$

__Induktionsschritt__:

Wir ergänzen einen Operator in unserer Formel

Wir unterscheiden zwischen zwei Fällen:

Ergänzung einer Negation:
$$A_{+1} = (\neg A)$$

Dann erhalten wir für $k(A_{+1})$:
$$\begin{align}
k(A_{+1}) &= k((\neg A))\\
&= 1 + k(A)
\end{align}$$

und für $op(A_{+1})$:
$$\begin{align}
op(A_{+1}) &= op((\neg A))\\
& = 1 + op(A)
\end{align}$$

Laut Induktionsvoraussetzung gilt $k(A) = op(A)$ also muss auch $1 + k(A) = 1 + op(A)$ gelten.

Ergänzung eines Binären Operators $\times$*:

$$C = (A \times B)$$

Wir erhalten für $k(C)$

$$\begin{align}
k(C) &= k((A\times B))\\
& = 1 + k(A)  + k(B)
\end{align}$$

und für $op(C)$

$$\begin{align}
op(C) &= op((A\times B))\\
& = 1 + op(A) + op(B)
\end{align}$$

nach Induktionsvoraussetzung gilt $k(A) + k(B) = op(A) + op(B)$,
dann gilt Trivial auch:
$$1 + k(A) + k(B) = 1 + op(A) + op(B)$$

$\blacksquare$

## Aufgabe 6

> Die Anzahl an Operatoren in einer Aussagenlogischen Formel ist mindestens 2 kleiner gleich der Anzahl an Variablen: $op(A) \geq v(A) - 2$

__Induktionsanfang__:

Wir betrachten den Fall mit keinem Operator:
$$A = p_i$$
dann gilt:
$$\begin{align}
op(A) \geq v(A) - 2\\
0 \geq 1 - 2\\
0 \geq -1
\end{align}$$

__Induktionsvoraussetzung__:
Es gelte für zwei beliebige aber feste $A, B\in F$:
$$op(A) \geq v(A) -2$$
$$op(B) \geq v(B) -2$$


Wir betrachten zwei Fälle:

Ergänzung eines Operators:
$A_{+1} = (\neg A)$

dann muss gelten:

$$\begin{align}
&op(A_{+1}) \geq v(A_{+1}) - 2\\
&\text{Da wir keine weitere Variable eingefuehrt haben gilt:}\\
\iff&op((\neg A)) \geq v(A) -2\\
\iff&1 + op(A) \geq v(A)-2
\end{align}$$

Da nach Induktionsvoraussetzung gilt: $op(A) \geq v(A) -2$  gilt Trivial auch $1+op(A) \geq v(A) -2$


Ergänzung eines Binären Operators $\times$:

$$C = (A \times B)$$

nach Definition muss gelten:
$$\begin{align}
op(C) &\geq v(C) - 2\\
1 + op(A) + op(B) &\geq v(A) + v(B) - 2\\
op(A) + op(B) &\geq v(A) + v(B) - 3
\end{align}$$

Durch die Induktionsvoraussetzung muss gelten:
$$op(A) + op(B) \geq v(A) + v(B) - 4$$
und da wir genau einen neuen Operator einführen um die beiden zu verbinden:
$$\begin{align}
1 + op(A) + op(B) \geq v(A) + v(B) -4\\
op(A) + op(B) \geq v(A) + v(B) -3
\end{align}$$
$\blacksquare$

> Es gibt immer eine Variable mehr als Binäre Operatoren in einer Aussagenlogischen Formel

__Induktionsanfang__

Wir betrachten eine Formel ohne Binäre Operatoren und einer Variable $A$:

Dann gilt:
$v(A) = 1$
und 
$1 + bop(A) = 1+0 = 1$
und damit
$$v(A) = 1 + bop(A)$$

__Induktionsvoraussetzung__:
Es gelte für zwei beliebige aber Feste $A, B\in F$ :
$$v(A) =  1+ bop(A)$$
$$v(B) = 1 + bop(B)$$

__Induktionsschritt__:

Wir betrachten die Ergänzung eines Binären Operators $\times$
$$C = A\times B$$
Dann gilt:
$$v(C) = 1 + v(A) + v(B)$$
und
$$bop(C) = 1 + bop(A) + bop(B)$$

nach Induktionsvoraussetzung gilt dann:
$$v(A) + v(B) = 2 + bop(A) + bop(B)$$
dann gilt Trivial:
$$1 + v(A) + v(B) = 2 + 1 + bop(A) + bop(B)$$

$\blacksquare$
