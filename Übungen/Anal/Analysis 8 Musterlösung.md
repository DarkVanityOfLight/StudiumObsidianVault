## Aufgabe 2
$$a_{n+1} = \sqrt{1 + a_n}$$

### a)

IA: $a_1 = 1 < 2$

IV: $a_n < 2$ für beliebiges n

IS:
$$\begin{align}
a_n <2 | + 1\\
a_n + 1 < 3\\
\sqrt{a_n + 1} < 3\\
a_{n+1} < \sqrt{3} < 2
\end{align}$$

### b)

IA:
$a_2 = \sqrt{2} > 1 = a_2$

IV: $a_{n+1} \ge a_n$
IS: $n \to n+1$
$$\begin{align}
a_{n+1} \ge a_n \\
\iff a_{n+1} + 1 \ge a_n +1\\
\iff \sqrt{a_{n+1} + 1} \ge \sqrt{a_n +1}\\
a_{n+2} > a_{n+1}
\end{align}$$


## Aufgabe 2

### a)
$\forall n \ge 2$ ist $c_n \ge \sqrt{d}$
IA: $c_2 = \frac{1}{2}(c_1 + \frac{d}{c_1}) = \frac{1}{2}(1 +d) > \sqrt{d}$
IV: $c_n \ge \sqrt{d}$
IS:
$$\begin{align}
c_n \ge \sqrt{d}
\iff c_n \ge \sqrt{\frac{d^2}{d}}\\
\iff c_n \ge \frac{d}{\sqrt d}\\
\iff \sqrt d \ge \frac{d}{c_n}\\
\implies c_n -\sqrt d \ge \sqrt d - \frac{d}{c_n}\\
\iff c_n + \frac{d}{c_n} \ge 2 \sqrt d = \sqrt d +\frac{d}{\sqrt d}\\
\end{align}$$

$$\begin{align}
c_{n+1} = \frac{1}{2}(c_m + \frac{d}{c_n}) \ge \frac{1}{2} (\sqrt d + \frac{d}{\sqrt d}) = \frac{1}{2}(\sqrt d + \sqrt d) = \sqrt d
\end{align}$$

### b)
$c_{n+1} \le c_n$

$$\begin{align}
c_n \ge \sqrt d \quad \forall n \ge 2\\
c_n^2 \ge d\\
2 c_n^2 \ge c_n^2 + d\\
2 c_n \ge c_n + \frac{d}{c_n}\\
c_m \ge \frac{1}{2}(c_n + \frac{d}{c_n}) = c_{n+1}
\end{align}$$

## Aufgabe 3

$$p (\frac{1}{1 - 10^r} - 1) 10^n$$

## Aufgabe 4

### a)


