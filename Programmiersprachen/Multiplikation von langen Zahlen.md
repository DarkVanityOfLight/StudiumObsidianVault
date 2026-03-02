$$\begin{array}{@{}c@{\;}c@{}c@{}c@{}c@{}c@{}}
& & & 3 & 1 & 2 \\
& & \times & 2 & 1 & 4 & 1 \\
\hline
& & &  & 3 & 1 & 2 \\
& & 1 & 2 & 4 & 8 & \\
 &  & 3 & 1 & 2 & & \\
 &  6& 2 & 4 &  & & \\
\hline
& 6 & 6 & 7 & 9 & 9 &2 \\
\end{array}$$

1. Wir berechnen $a_{i} \cdot \beta$ für alle $i=0,..., n-1$
	__Elementaroperation__ Zwei Ziffern multiplitzieren

$$a_{i}\cdot \beta = c_{i} \cdot B + d_{i}$$
$n$ Elem.-operationen

2. Wir berechnen die Summe von $c_{n-1}...c_{0}0$ und $d_{n-1}...d_{0}$
$n$ Elem.operationen

$$\begin{align}
&\text{Input: } \text{Two integers } a = a_{n-1}a_{n-2} \dots a_0 \text{ and } b = b_{n-1}b_{n-2} \dots b_0 \text{ in base 10} \\
&\text{Output: } \text{The product } a \cdot b \text{ in base 10}
\\
&s \leftarrow 0 \\
&\text{for } j \leftarrow 0 \text{ to } n-1 \text{ do:} \\
&\qquad p \leftarrow \text{multZiffer}(a, b_j) \\
&\qquad s \leftarrow \text{add}(s, p \cdot 10^{j}) \\
&\text{return } s
\end{align}$$

Wir können zwei $n$-stellige Zahlen $x, y$ mit $4n^{2}$ elementaren Operationen zu einer $2n$-Stelligen Zahl $x \cdot y$ multiplizieren.

__Beweis__

In jeder Iteration benötigen wir:
- $2n$ Elementaroperationen für `multZiffer(.,.)`
- $\le 2n$ Elemenatroperationen für `add(.,.)`, denn:
	-  $s$ und $pB^{j}$ sind höchstens $(n+j+1)$-stellig
	- $n+j+1 \le 2n$
	- `add(.,.)` benötigt $N$ Elementaroperationen für $N$-stellige Zahlen
	- Über alle $n$ Iterationen sind das höchstens $n \cdot (4n) = 4n^2$ Elementaroperationen.

