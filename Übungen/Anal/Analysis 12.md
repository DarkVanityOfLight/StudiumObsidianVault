## Aufgabe 1
## Aufgabe 1

### a)


$$f(x)=\frac{x^2}{x^3-1}$$
$$\begin{align}
0&=\frac{x^2}{x^3-1} \\
0&=x^2 = x \\ \\
0&=x^3 - 1  \\
1&=x^3 \\
1&=x \\
\end{align}$$
$$\implies \text{Nullstelle bei } x=0$$

---

$$\begin{align}
f(x)&=\frac{x^2}{x^3-1} \\
f'(x)&=\frac{x \cdot (x^3-1)-x^2\cdot 3x^2}{(x^3-1)^2} \\ 
f'(x)&=\frac{-x^4-2x}{(x^3-1)^2} \\
0&=\frac{-x^4-2x}{(x^3-1)^2} \\
x&=0 \\
x&=-\sqrt[3]{2} \\
\\
f''(x)&=\frac{2(x^6+7x^3+1)}{(x-1)^3(x^2+x+1)^3} \\
-2&=\frac{2(0^6+7\cdot0^3+1)}{(0-1)^3(0^2+0+1)^3} \\
-2&<0 \\ \\
&\text{Lokales Maximum: }(0, 0) \\ \\
&\text{Lokales Minimum: }(-\sqrt[3]{2}, -\frac{\sqrt[3]{4}_3}{3}) \\ 
\end{align}$$

### b)

Bestimmen Sie die Grenzwerte:

$$\lim_{x \to \infty}\frac{x^2}{x^3-1}$$
$$\lim_{x\to \infty}\frac{x^2}{x^3-1}$$


$$\lim_{x \to \infty}\frac{x^2}{x^3-1}=\lim_{x \to \infty}\frac{x^2}{x^3}\cdot\frac{1}{1-\frac{1}{x^3}}$$ Da $\lim_{x \to \infty}x^2=\infty$ und $\lim_{x \to \infty}x^{-3}=0$, ist $\lim_{x \to \infty}\frac{x^2}{x^3}=\infty$.

---

$$\lim_{x \to -\infty}\frac{x^2}{x^3-1}=\lim_{x \to -\infty}\frac{x^2}{x^3}\cdot\frac{1}{1-\frac{1}{x^3}}$$ Da $\lim_{x \to -\infty}x^2=\infty$ und $\lim_{x \to -\infty}x^{-3}=0$, ist $\lim_{x \to -\infty}\frac{x^2}{x^3}=\infty$.

---

Wenn $x$ gegen $-\infty$ geht und $x<1$ ist dann muss $x^3<1$ und damit ist $x^3-1<0$. Daher ist auch $\frac{x^2}{x^3-1}<0$.
 
---

Wenn $x$ gegen $-\infty$ geht und $x>1$ ist dann muss $x^3>1$ und damit ist $x^3-1>0$. Daher ist auch $\frac{x^2}{x^3-1}>0$.

### c)
![](Pasted%20image%2020230207205558.png)

### d) 
Wolfram Alpha gibt uns:

![](Pasted%20image%2020230207205815.png)

![](Pasted%20image%2020230207205821.png)


## Aufgabe 2

$$\begin{align*}\\
&\lim_{x\to\infty} \frac{exp(x)-exp(-x)}{exp(x)+exp(-x)}\\
\iff&\lim_{x\to\infty} \frac{e^{x}-e^{-x}}{e^{x}+e^{-x}}\\
&e^{-x} = \frac{1}{e^{x}} \to\text{wenn}\; x\to\infty \frac{1}{e^{x}} = 0\\
&\lim_{x\to\infty} \frac{e^{x}}{e^{x}} = 1
\end{align*}$$
Die beiden $e^{-x}$ gehen richtung $0$ wenn $x\to\infty$ also bleibt so nur noch $\frac{e^{x}}{e^{x}}$ und die sind gleichgroß somit $1$

$$
\lim_{x\to 1} \frac{\ln(x)}{1-x}

$$
$ln(x)$ geht in Richtung $0$. $1-x$ geht in Richtung $0$. Wir teilen also eine unendlich kleine Zahl durch eine unendlich kleine Zahl und erhalten als Grenzwert $-1$ (da der Zähler negativ und der Nenner positiv ist)

## Aufgabe 3

$$
\begin{align*}
\lim_{\begin{array}{}x\to 0 \\ x >0\end{array}} x (\ln x)^{n}= 0\\
\end{align*}
$$
Da $x$ gegen $0$ geht multiplizieren wir quasi $-\infty^{n}$ mit $0$. Daraus folgt das 
$\lim_{\begin{array}{}x\to 0 \\ x >0\end{array}} x (\ln x)^{n}$ gegen $0$ geht.
