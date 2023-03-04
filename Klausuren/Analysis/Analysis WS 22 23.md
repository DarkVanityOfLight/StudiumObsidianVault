## Aufgabe 1

Zeigen Sie, dass 
$$\sum\limits^{n}_{k=1} (2k-1) = n^{2}$$
für alle natürlichen Zahlen $n \ge 1$

---

__Induktionsbehauptung__:

$$A: \sum\limits^{n}_{k=1} (2k-1) = n^{2}$$
__Induktionsanfang__:

$$\begin{align*}
\sum\limits^{1}_{k=1} (2k-1) &=  1\\
1^{2} &=  1
\end{align*}$$

__Induktionsvoraussetzung__:

Für ein beliebiges, aber festes $n\in\mathbb N, n \ge 1$ gelte $A(n)$.

__Induktionsschritt__

$$n\mapsto n+1$$
$$n^{2} \mapsto (n+1)^2$$

$$\begin{align*}
&\sum\limits^{n+1}_{k=1} (2k-1)\\
\iff &\underbrace{\sum\limits^{n}_{k=1} (2k-1)}_{IV} + (2(n+1))\\
\iff &n^{2} + 2n + 2\\
\iff &(n+1)^{2}\\
\blacksquare
\end{align*}$$

## Aufgabe 2

Sei $f: \mathbb R\to\mathbb R$ mit
$$f(x) = \frac{\exp(x)-1}{\exp(x)+1}$$
Bestimmen Sie die Grenzwerte $\lim_{x\to\infty} f(x)$ und $\lim_{x\to-\infty} f(x)$ und die Nullstellen von $f$. Skizzieren Sie den Graphen von $f$.

Bestimmen Sie für $n\in\mathbb N_{0}$ den Grenzwert
$$\lim_{x\to \infty} \frac{x^{n}}{exp(x)}$$

---

__Grenzwerte:__
$$\begin{align*}
\lim_{n\to\infty} f(x) &= \lim_{n\to\infty} \frac{\exp(x) - 1}{\exp(x) + 1}\\
&= \lim_{n\to\infty} \frac{\frac{\exp(x)}{\exp(x)} - \frac{1}{\exp(x)}}{\frac{\exp(x)}{\exp(x)} + \frac{1}{\exp(x)}}\\
&= \frac{\lim_{n\to\infty}\frac{\exp(x)}{\exp(x)} - \lim_{n\to\infty}\frac{1}{\exp(x)}}{\lim_{n\to\infty}\frac{\exp(x)}{\exp(x)} + \lim_{n\to\infty}\frac{1}{\exp(x)}}\\
&= \frac{1 - \lim_{n\to\infty} \exp(-x)}{1+ \lim_{n\to\infty}\exp(-x)}\\
&= -1
\end{align*}$$
$$\begin{align*}
\lim_{n\to-\infty} f(x) &= \lim_{n\to-\infty} \frac{\exp(x) - 1}{\exp(x) + 1}\\
&= \lim_{n\to-\infty} \frac{\frac{\exp(x)}{\exp(x)} - \frac{1}{\exp(x)}}{\frac{\exp(x)}{\exp(x)} + \frac{1}{\exp(x)}}\\
&= \frac{\lim_{n\to-\infty}\frac{\exp(x)}{\exp(x)} - \lim_{n\to-\infty}\frac{1}{\exp(x)}}{\lim_{n\to-\infty}\frac{\exp(x)}{\exp(x)} + \lim_{n\to-\infty}\frac{1}{\exp(x)}}\\
&= \frac{1 - \lim_{n\to-\infty} \exp(-x)}{1+ \lim_{n\to-\infty}\exp(-x)}\\
&= 1
\end{align*}$$
__Nullstellen:__

$$\begin{align*}
0 &= \frac{\exp(x) - 1}{\exp(x) + 1} &|& \cdot (\exp(x) + 1)\\
0 &= \exp(x) - 1 &|& + 1\\
1 &= \exp(x) &|&\ln\\
\ln 1 &= x\\
x &= 0
\end{align*}$$

---

$$\begin{align*}
&\lim_{n\to\infty} \frac{x^{n}}{\exp(x)}\\
\iff & \lim_{n\to\infty} \frac{x^{n}}{\exp(x)}\\
\iff & \lim_{n\to\infty} \frac{x^{n}}{1} \cdot \lim_{n\to\infty} \frac{1}{\exp(x)} &= 0
\end{align*}$$

## Aufgabe 3

Untersuchen Sie die folgenden Reihen auf Konvergenz, und bestimmen Sie gegebenenfalls den Grenzwert

$$\sum\limits^{\infty}_{n=0} (-1)^{n} \frac{1}{2^{n}} \qquad \sum\limits^{\infty}_{n=1} \frac{1}{\sqrt{n}}$$
Untersuchen Sie, für welche $x\in\mathbb R$ die Reihe
$$\sum\limits^{\infty}_{n=1} n \cdot x^{n}$$
konvergiert, und bestimmen Sie den Grenzwert.

---

$$\begin{align*}
\sum\limits^{\infty}_{n=0}(-1)^{n} \frac{1}{2^{n}}\\
\sum\limits^{\infty}_{n=0 } \frac{(-1)^{n}}{2^{n}}\\
\sum\limits^{\infty}_{n=0} \left(\frac{-1}{2}\right)^{n}\\
&= \frac{1}{1--\left(\frac{1}{2}\right)}\\
&= \frac{1}{\frac{3}{2}} = \frac{2}{3}
\end{align*}$$

$$\begin{align*}
\sum\limits^{\infty}_{n=1} \frac{1}{\sqrt{n}}\\
\sum\limits^{\infty}_{n=1} \frac{1}{n^{\frac{1}{2}}} &\ge \sum\limits^{\infty}_{n=1} \frac{1}{n} \implies\text{Divergent}
\end{align*}$$

---



## Aufgabe 4

Sei $a\in\mathbb R$ und $f_{a} : \mathbb R \to\mathbb R$ mit
$$f_{a}(x) = x^{4} - a \cdot x^{2}$$

1. Bestimmen Sie für jedes $a$ die Anzahl der Nullstellen von $f_{a}$
2. Bestimmen Sie für jedes $a$ die lokalen Minima und Maxima von $f_{a}$
3. Erstellen Sie jeweils eine qualitative Skizze des Graphen von $f_{-1}, f_{0}$ und $f_{1}$

---

$$\begin{align*}
0 &= x^{4} - a\cdot x^{2}\\
0 &= x^{2} \cdot (x^{2} - a)\\
0 &= x^{2} \land 0 = x^{2}-a 
\end{align*}$$

Falls $a=0$ gibt es eine Nullstelle bei $x=0$.
Falls $a > 0$ gibt es drei Nullstellen bei $x=0, x = +\sqrt{a}, x = -\sqrt{a}$.
Falls $a< 0$ gibt es eine Nullstelle bei $x=0$.

---

$$\begin{align*}
f_{a}(x) &= x^{4} -a \cdot x^{2}\\
f'_{a}(x) &= 4x^{3}- 2ax\\
f''_{a}(x) &= 12x^{2} - 2a
\end{align*}$$

$$\begin{align*}
0 &= 4x^{3} - 2ax\\
2ax &= 4x^{3}\\
2a &= 4x^{2}\\
a &= 2x^{2}\\
\frac{a}{2} &= x^2\\
\pm\sqrt{\frac{a}{2}} &= x
\end{align*}$$
Falls $a=0$ gibt es ein Maximum/Minimum bei $x=0$.
Falls $a > 0$ gibt es drei Maxima/Minima bei $x=0, x=+\sqrt\frac{a}{2}, x = -\sqrt{\frac{a}{2}}$.
Falls $a<0$ gibt es ein Maximum/Minimum bei $x=0$

