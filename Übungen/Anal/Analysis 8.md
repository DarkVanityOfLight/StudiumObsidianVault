> Kilian Lichtner, Jannis Lichtner

## Aufgabe 1

$$
(a_{n+1}) = \sqrt{1+a_n}
$$
## a)
$$
0 \leq a_n < 2
$$

IA:
$$0 \leq a_1 = 1 < 2$$
IV: $0 \leq a_n < 2$ gelte für ein beliebiges aber festes $n \in\mathbb N$

IS:$n\to n+1$
1.
$$\begin{align}
&0 \leq a_n\\
\implies&0 \leq a_{n+1} =\sqrt{1 + a_n}\\
&\underbrace{\geq}_{IV} \sqrt{1 + 0}\\
\implies & 0 \leq a_{n+1} = \sqrt{1}
\end{align}$$
2.
$$\begin{align}
&a_n < 2\\
\implies &a_{n+1} = \sqrt{1 + a_n} \underbrace{<}_{IV} \sqrt{1 + 2} = \sqrt{3}\\
\implies  & a_{n+1} = \sqrt{3} < 2
\end{align}$$



### b)
Wenn eine Folge monoton Steigend ist muss gelten $a_n < a_{n+1}$
IA: 
$a_2 \ge a_1$
$\sqrt{1 + 1} \geq 1$

IV: Gelte $a_n \ge a_{n-1}$ für irgendeine feste natürliche Zahl $n$.
IS: $n \to n+1$
$a_{n+1} \ge a_n$. Da $a_{n+1} = \sqrt{1 + a_n}$ und $a_n \ge a_{n-1}$ nach Annahme, müssen wir zeigen, dass $\sqrt{1 + a_n} \ge a_n$.

 Wenn $a_n > 0$, dann gilt $1 + a_n > a_n$ und daher $\sqrt{1+a_n} > \sqrt{a_n}$. Da $\sqrt{a_n} = a_n$ folgt $\sqrt{1 + a_n} > a_n$.


## Aufgabe 2

### a)
IA:
Für $n = 1$ gilt $c_1 = 1 \ge \sqrt{d}$. 

IV: Gelte für ein beliebiges aber Festes $n \in \mathbb N$ $c_n \geq \sqrt{d}$

IS:$n \to n+1$
$$c_{n+1} = \frac{1}{2}(c_n + \frac{d}{c_n}) \underbrace{\ge}_{IV} \frac{1}{2}(\sqrt{d} + \frac{d}{\sqrt{d}}) = \sqrt{d}$$
### b)
Wenn eine Funktion monoton fallend ist muss gelten $c_{n+1} < c_n$

Damit gilt $c_{n+1} -c_n \geq 0$
$$\begin{align}
&c_{n+1} - c_n = \frac{1}{2}(c_n + \frac{d}{c_n}) -  c_n\\
& = \frac{1}{2}(c_n + \frac{d}{c_n} - 2c_n)\\
& = \frac{1}{2}(\frac{d}{c_n} - c_n)\\
& = \frac{1}{2}(\frac{d}{c_n} - \frac{(c_n)^2}{c_n})\\
& = \frac{1}{2}(\frac{d - (c_n)^2}{c_n})\\
& = \frac{d - (c_n)^2}{2c_n}
\end{align}$$
Wir wissen $c_n$ wird minimal $\sqrt{d}$ also
$$\begin{align}
&\frac{d - (c_n)^2}{2c_n}\\
=&\frac{d - (\sqrt{d})^2}{2 \sqrt{d}}\\
=& \frac{0}{2\sqrt{d}} = 0 \geq 0
\end{align}$$



## Aufgabe 3

$r_1 = 0.5\overline{5} = \frac{5}{9}$
$r_2 = 0.36\overline{36} = \frac{36}{99}$
$r_3 = 0.0483\overline{483} = \frac{483}{9999}$
$r_4 = 0.692307\overline{692307} = \frac{692307}{999999}$

## Aufgabe 4

### a)
$$\begin{align}
&\sum^{\infty}_{n = 1} (3^{-n} + 5^{-n})\\
&\text{Quotienten kriterium}\\
&\lim_{n\to \infty}|\frac{a_{n+1}}{a_n}|\\
&\left|\frac{3^{-(n+1)} + 5^{-(n+1)}}{3^{-n} + 5^{-n}}\right| \\
&= \frac{3^{-(n+1)} + 5^{-(n+1)}}{3^{-n} + 5^{-n}}\\ 
&= \frac{3^{-n-1} + 5^{-n-1}}{3^{-n} + 5^{-n}} \\
&= \frac{1}{3}+\frac{1}{5} \qquad\implies\text{Konvergent}
\end{align}$$

Grenzwert: 

$$
\frac{1}{2}\left(\frac{1}{1-\frac{1}{3}}\right) + \frac{1}{2}\left(\frac{1}{1-\frac{1}{5}}\right) = \frac{3}{4} + \frac{5}{8} = \frac{24}{32} + \frac{40}{40} = \frac{64}{40} = \frac{8}{5}
$$


### b)

$$\begin{align}
&\sum^{\infty}_{n=1} \frac{2^{n-1}}{3^n}\\
&\text{Quotientenkriterium}\\
&\lim_{n\to \infty} |\frac{a_{n+1}}{a_n}|\\
&\lim_{n\to \infty} |\frac{\frac{2^n}{3^{n+1}}}{\frac{2^{n-1}}{3^n}}|\\
&\lim_{n\to \infty} |\frac{2^n}{3^{n+1}} \cdot \frac{3^n}{2^{n-1}}|\\
&\lim_{n\to \infty} |\frac{2^n \cdot 3^n}{3^{n+1} \cdot 2^{n-1}}|\\
&\lim_{n\to \infty} |\frac{2^n \cdot 3^n}{3^n \cdot 3^1 \cdot 2^n \cdot 2^{-1}}\\
&\lim_{n \to \infty} |\frac{2 \cdot 2^n \cdot 3^n}{3^n \cdot 3 \cdot 2^n}|\\
&\lim_{n\to\infty} |\frac{2}{3}| < 1 \quad \implies \text{Konvergent}
\end{align}$$
Grenzwert: $\frac{2^{1-1}}{3^1} + \frac{2^{2-1}}{3^2} + \frac{2^{3-1}}{3^3} + \frac{2^{4-1}}{3^4} + \frac{2^{5-1}}{3^5} + \frac{2^{6-1}}{3^6} + \frac{2^{7-1}}{3^7} + \frac{2^{8-1}}{3^8} + \frac{2^{9-1}}{3^{9}} + \frac{2^{10-1}}{3^{10}} + \frac{2^{11-1}}{3^{11}} \approx 1$

### c)
$$\begin{align}
&\sum^{\infty}_{n=0} (-1)^n \frac{n!}{2^n}\\
&\text{Quotientenkriterium}\\
&\left|\frac{(-1)^{n+1} \frac{(n+1)!}{2^{n+1}}}{(-1)^n \frac{n!}{2^n}}\right|  = \frac{n+1}{2}\\
&\lim_{n\to\infty}\frac{(n+1)}{2} = \infty \implies \text{Divergent}
\end{align}$$

### d)
$$\begin{align}
&\sum^{\infty}_{n = 3} \frac{2}{n^2 - 2n}\\
&\text{Majorantenkriterium}\\
&0 < \frac{2}{n^2 - 2n} < \frac{1}{n}\\
&\text{$\frac{1}{n}$ konvergiert} \implies \sum^{\infty}_{n = 3} \frac{2}{n^2 - 2n} \text{konvergiert} 
\end{align}$$
Grenzwert:
$$\begin{align}
&\frac{2}{3^2-2\cdot3} + \frac{2}{4^2-2\cdot4} + \frac{2}{5^2-2\cdot5} + \frac{2}{6^2-2\cdot6} + \frac{2}{7^2-2\cdot7}\\
&+ \frac{2}{8^2-2\cdot8} + \frac{2}{9^2-2\cdot9} + \frac{2}{10^2-2\cdot10} + \frac{2}{11^2-2\cdot11} + \frac{2}{12^2-2\cdot12} \\
&+ \frac{2}{13^2-2\cdot13} + \frac{2}{14^2-2\cdot14} + \frac{2}{15^2-2\cdot15} + \frac{2}{16^2-2\cdot16} + \frac{2}{17^2-2\cdot17} \\
&+ \frac{2}{18^2-2\cdot18} + \frac{2}{19^2-2\cdot19} + \frac{2}{20^2-2\cdot20} + \frac{2}{21^2-2\cdot21} + \frac{2}{22^2-2\cdot22} \\
&+ \frac{2}{23^2-2\cdot23} + \frac{2}{24^2-2\cdot24} + \frac{2}{25^2-2\cdot25} + \frac{2}{26^2-2\cdot26} + \frac{2}{27^2-2\cdot27} \\
&+ \frac{2}{28^2-2\cdot28} + \frac{2}{29^2-2\cdot29} + \frac{2}{30^2-2\cdot30} + \frac{2}{31^2-2\cdot31} + \frac{2}{32^2-2\cdot32} \\
&+ \frac{2}{33^2-2\cdot33} + \frac{2}{34^2-2\cdot34} + \frac{2}{35^2-2\cdot35} + \frac{2}{36^2-2\cdot36} + \frac{2}{37^2-2\cdot37} \\
&+ \frac{2}{38^2-2\cdot38} + \frac{2}{39^2-2\cdot39} + \frac{2}{40^2-2\cdot40} \approx 1.5
\end{align}$$
