
## Aufgabe 1

### a)

$$
\sum\limits^{k}_{n=1} x^{n}= \frac{x-x^{k+1}}{1-x}
$$
fuer $k\ge 1$

IA: 
$\sum\limits^{1}_{n=1} x^{n}= x$
$\frac{x-x^{1+1}}{1-x} = \frac{-x^{2} +x}{1-x} =  \frac{-x\cdot (x-1)}{-x + 1} = \frac{-x \cdot (x-1)}{-(x-1)} = \frac{-x}{-1} = x$

IV: Fuer ein beliebiges aber festes $k\in \mathbb N$ gelte $A(k)$$

$$
\frac{x-x^{2}}{1-x}
$$
IS: $k\to k+1$
$$\begin{align*}
&\sum\limits^{k+1}_{n=1} x^n\\
&\sum\limits^{k}_{n=1} x^n +x^{k+1}\\
&\frac{x-x^{k+1}}{1-x} +x^{k+1}\\
&\frac{x-x^{k+1}}{1-x} + \frac{x^{k+1} \cdot 1-x}{1-x}\\
&\frac{x-x^{k+1} +x^{k+1} \cdot 1-x}{1-x}\\
&\frac{x \cdot (1-x)}{1-x}\\
&\frac{x-x^{2}}{1-x}
\end{align*}$$

### b)
Da gilt $\lim_{k\to\infty} x^{k+1} = 0$ mit $|x|< 1$ gilt $\lim_{k\to\infty} \frac{x-x^{k-1}}{1-x} = \frac{x-0}{1-x} = \frac{x}{1-x}$


### c)
 $0.\overline{27} = \frac{27}{99}$


## Aufgabe 2
### a)
$$
(x_1, y_1) \sim (x_2, x_2) \iff f(x_1, y_1) = f(x_2, y_2)\\
$$

__Reflexiv__:
Da eine Abbildung eindeutig ist muss gelten:
$f(x_{1}, y_{1})= f(x_{1}, y_{1}) \forall (x_{1}, y{1}) \in \mathbb R^2$

__Transitiv__:
$$\begin{align*}
(x_1, y_1) \sim (x_2, y_2)\\
(x_2, y_2) \sim (x_3, y_3)\\
\implies(x_1, y_1)\sim(x_3, y_3)
\end{align*}$$
muss gelten da
$f(x_{1}, y_{1}) = f(x_{2}, y_{2}) = f(x_{3}, y_{3})$
impliziert das alle drei Elemente das selbe sind, da eine Abbildung eindeutig ist.

__Symmetrisch__:
$(x_{1}, y_{1}) \sim (x_{2}, y_{2}) \implies (x_{2}, y_{2}) \sim (x_{1}, y_{1})$
da
$f(x_{1}, y_{1}) = f(x_{2}, y_{2}) \implies f(x_{2}, y_{2}) = f(x_{1}, y_{1})$
da die Abbildung eindeutig ist.


### b)
$$\begin{align*}
f(x, y) = x^{2} - y\\
f(0, 0) = 0^2 - 0 = \overline 0\\
f(1, -1) = 1^2 - (-1) = \overline 2\\
f(1, 1) = 1^2 - 1 = \overline 0
\end{align*}$$
4

### b)

$$
\begin{align*}\\
&\sum\limits^{\infty}_{n=1} \frac{n^{3}}{2^n}\\
&\text{Quotientenkriterium}\\
& \frac{\frac{(n+1)^3}{2^{n+1}}}{\frac{n^{3}}{2^{n}}}\\
&\frac{(n+1)^3}{2^{n+1}} \cdot \frac{2^{n}}{n^{3}}\\
&\frac{2^n}{2^{n+1}} \cdot \frac{(n+1)^3}{n^3}\\
&2^{n-n+1} \cdot (\frac{n+1}{n})^3\\
&2^{1} \cdot \frac{1}{n} + 1\\
&\lim_{n\to\infty}2\cdot \frac{1}{n} + 1\\
&
\end{align*}
$$