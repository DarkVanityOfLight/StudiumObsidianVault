> Kilian Lichtner, Jannis Lauterbach

## Aufgabe 1

$$\begin{align*}
&\left(\underbrace{\sum\limits^{\infty}_{n=1} \frac{(-1)^{n-1}}{n}}_{\text{Logarithmus reihe}} x^{n}\right)'\\
&\iff (\log(x+1))'\\
&\iff \frac{1}{1+x}
\end{align*}$$

$$
\begin{align*}
&\sum\limits^{\infty}_{n=0} n^{2} x^{n} = \frac{x \cdot (1 + x)}{(1-x)^{3}}\\
&x \frac{d}{dx} x \frac{d}{dx} \sum\limits^{\infty}_{n=0} x^{n} =  x \frac{d}{dx} x \frac{d}{dx} \frac{1}{1-x} = x \frac{d}{dx} \frac{x}{(1-x)^{2}}= \frac{x(1+x)}{1-x^3}
\end{align*}
$$

## Aufgabe 2
Sei $a \in \mathbb R$
$$\begin{align}
(f + g)'(a) &= \lim{x \to a} \frac{f(x) + g(x) - (f(a) + g(a))}{x-a} \\&= \lim{x \to a} \left( \frac{f(x) - f(a)}{x-a} + \frac{g(x) - g(a)}{x-a} \right) \\= f'(a) + g'(a)
\end{align}$$

## Aufgabe 3

$$\sum\limits^{\infty}_{n=0} a_{n}\cdot x^{n}$$

$r(P) = \frac{1}{\lim_{n\to\infty} |a_n|^\frac{1}{3}}$

$a_{1} = 2 \cdot a_{0} + 1 = 1$
$a_{2}= 2\cdot a_{1} + 1 = 3$
$a_{3}= 2 \cdot a_{2} + 1 = 7$

Diese ist eine expotentielle Wachstumsfolge, so dass
$a_{n}^{\frac{1}{n}} \to n$ , wenn $n\to\infty$

$r(P) = \frac{1}{\lim_{n\to\infty} |a_n|^{\frac{1}{n}}} = \frac{1}{2}$

### b)

$a_n$ durch $x^{n}$ ersetzen und Potenzreihe mit einer geometrischen Reihe verbinden 
$P(x) = \sum\limits^{\infty}_{n=0} a_{n}\cdot x^{n} = x^{0} + (2 \cdot x^{0} +1) \cdot x + (2\cdot (2\cdot x^{0} +1 )) \cdot x^{2} + ...$

somit bringen wir $P(x)$ in die Form einer geometrische Reihe.
Da jeder Term von $P(x)$ das Ergebnis der Multiplikation von $x^{n}$
mit einer konstanten ist, die sich durch $a_{n+1} = 2\cdot a_{n}+1$ berechnet.
Daher können wir jedem Term in $P(x)$ als von $x^{n}$ in einer geometrische Reihe darstellen.
Also kann man $P(x)$ als Produkt von $x$ und einer geometrischen Reihe darstellen.

$S_{1}$ berechnen

$$\begin{align*}
S_{1} &= 1 + (2 \cdot x^{0} + 1) \cdot x + (2\cdot(2\cdot x^{0}+ 1)) \cdot x^{2}+ ...\\
&= 1 + x \cdot (2 + x\cdot(n + x \cdot (8 + ...)))\\
&= 1 + x \cdot (\frac{2}{1-2x })
\end{align*}$$
$P(x) = x \cdot S_{1} = x \cdot \left(1 + x \cdot \left(\frac{2}{1-2x}\right)\right)= \frac{x}{(1-2x)(1-x)}$ solange $|x| < \frac{1}{2}$

## Aufgabe 4

### a)

$$x{n+1}=x{n}-\frac{f(x_n)}{f'(xn)}$$

$$f(x)=x^2-2$$

$$f'(x)=2x$$

Wenn wir in die Stammfunktion $\sqrt2$ einsetzten können wir feststellen, dass wir für $f(\sqrt{2})=\sqrt{2}^2-2$ wir als Lösung $0$ bekommen, somit ist die Funktion stetig.

Mithilfe von dem Newtonverfahren können wir uns langsam dem Grenzwert annähern:
$$\begin{align}
x{n}-\frac{x^2-2}{2x} 
\end{align}$$

$$\begin{matrix}
1 & 2 & 3 & 4 \\
\frac{3}{2} & \frac{17}{12} & \frac{577}{408} & \frac{665857}{470823}  \end{matrix}$$

Anhand von der Tabelle lässt sich Feststellen, dass die Folge $(x_n)$ gegen $\sqrt2$ geht.

### b)

1. $x_1=1$
2. $x_2 = x_1 - \frac{f(x_1)}{f'(x_1)} = 1 - \frac{1^2-2}{2 \cdot 1} = 1.5$
3.  $x_3 = x_2 - \frac{f(x_2)}{f'(x_2)} = 1.5 - \frac{1.5^2-2}{2 \cdot 1.5} = 1.41667$
4.  $x_4 = x_3 - \frac{f(x_3)}{f'(x_3)} = 1.41667 - \frac{1.41667^2-2}{2 \cdot 1.41667} = 1.41421$
5.  $x_5 = x_4 - \frac{f(x_4)}{f'(x_4)} = 1.41421 - \frac{1.41421^2-2}{2 \cdot 1.41421} = 1.41421$
6.  $x_6 = x_5 - \frac{f(x_5)}{f'(x_5)} = 1.41421 - \frac{1.41421^2-2}{2 \cdot 1.41421} = 1.41421$