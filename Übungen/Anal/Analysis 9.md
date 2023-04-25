> Jannis Lauterbach, Kilian Lichtner
## Aufgabe 1

$$\begin{align}
&\sum\limits^{\infty}_{n=1} \frac{(1 + (-1)^{n} \cdot \frac{1}{2})^{n}}{n^{2}}\\
&\sum\limits^{\infty}_{n=1} \frac{(1 + (-1)^{n} \cdot \frac{1}{2})^{n}}{1} \cdot \frac{1}{n^{2}}\\
&\sum\limits^{\infty}_{n=1} \underbrace{(1 + (-1)^{n} \cdot \frac{1}{2})^{n}}_{\text{Alterniert zwischen 1 und 0}} \cdot \underbrace{\frac{1}{n^{2}}}_{\text{Allgemeine Harmonische Reihe}}\\
\implies \text{Konvergiert}
\end{align}
$$


$$\begin{align}
&\sum\limits^{\infty}_{n=0}\frac{n^5}{5^{n}}\\
&\text{Quotientenkriterium}\\
&\lim_{n\to\infty} |\frac{a_{n+1}}{a_{n}} |\\
&\lim_{n\to\infty} |\frac{\frac{(n+1)^5}{5^{n +1}}}{\frac{n^5}{5^{n}}}|\\
&\lim_{n\to\infty} | \frac{(n+1)^{5}}{5^{n+1}} \cdot\frac{5^{n}}{n^{5}}|\\
&\lim_{n\to\infty} |\frac{(n+1)^{5} \cdot 1}{ 5^{n+1} \cdot 5^{-n} \cdot n^{5}}|\\
&\lim_{n\to\infty} |\frac{(n+1)^{5}}{ 5 \cdot n^{5}}|\\
&\lim_{n\to\infty} |\frac{1}{5} \cdot \frac{(n+1)^{5}}{  n^{5}}|\\
&\lim_{n\to\infty} |\frac{1}{5} \cdot \left(\frac{(n+1)}{n}\right)^5|\\
&\lim_{n\to\infty} |\frac{1}{5} \cdot\left(\frac{n}{n} \cdot\frac{1}{n}\right)^5|\\
&\lim_{n\to\infty} |\frac{1}{5} \cdot\left(1 \cdot\underbrace{\frac{1}{n}}_{0}\right)^5|\\
&\implies \frac{1}{5} < 1\\
&\implies \text{Konvergiert}
\end{align}$$
## Aufgabe 2

$$\begin{align}
&\sum\limits^{\infty}_{n=3} = \frac{n+4}{(n-1)(n-2)}\\

\end{align}$$

$$\sum\limits^{\infty}_{n=3} \frac{1}{n}$$

$\lim\limits_{n\to\infty} \frac{\frac{n+4}{(n-1)(n-2)}}{\frac{1}{n}} = \lim\limits_{n\to\infty} \frac{n+4}{n} = \infty$
$\implies$ Divergent

## Aufgabe 3

$$\begin{align}
&\sum\limits^{\infty}_{n=0}\frac{(-1)^n}{3-2n}\\
&\sum\limits^{\infty}_{n=0}(-1)^n \underbrace{\frac{1}{3-2n}}_{\text{Geometrische Reihe}}\\
&\text{Leibnizkriterium}
\implies \text{Konvergent}
\end{align}$$

## Aufgabe 4

$x\in\mathbb R$
$$
P(x) = \sum\limits^{\infty}_{n=0} \frac{1}{3^{n}}x^n
$$
$$
r = \frac{1}{\lim_{n\to\infty}\sqrt[n]{|a_n|}}
$$

$$
\lim \sqrt[n]{|\frac{1}{3^{n}|}}= \lim_{n\to\infty}\sqrt[n]{\frac{1}{3^{n}}} = \lim_{cn\to\infty}\frac{1}{\sqrt[n]{3^{n}}}= \frac{1}{3}
$$

$$ r = \frac{1}{\frac{1}{3}} = 3$$
$$x_{0}= x^n$$
$$|x - 0| < 3 \qquad |x-x_{0}|< 3$$
$$-3 < x < 3$$
Die Reihe Konvergiert für $-3 < x < 3$