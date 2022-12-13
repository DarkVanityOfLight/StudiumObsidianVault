
## Aufgabe 1

### a)

Sein $\epsilon > 0$ beliebig und betrachte $|a_n - 0|$:
$$|{1\over a_n} - a| = |{1\over n} - 0| = {1\over n} < {p\over q} = \epsilon \ \text{fuer alle $n\geq$ N := q+1}$$

### b)
$$a_n = {(-1)^n \over n}$$


## Aufgabe 2
### a)
Bei der vorliegenden Folge handelt es sich um die "Fibonacci Folge", die Rekursionsgleichung lautet: $f_n = f_{n-1} + f_{n-2}$

Berechnung von $f_{11}$ :
$$\begin{align}
&f_0 = 0 \qquad &&f_1 = 1 \\
&f_2 = f_1 + f_0 = 1 + 0 = 1 \qquad &&f_3 = f_2 + f_1 = 1 + 1 = 2 \\
&f_4 = f_3 + f_2 = 2 + 1 = 3 \qquad &&f_5 = f_4 + f_3 = 3 + 2 = 5 \\
&f_6 = f_5 + f_4 = 5 + 3 = 8 \qquad &&f_7 = f_6 + f_5 = 8 + 5 = 13 \\
&f_8 = f_7 + f_6 = 13 + 8 = 21 \qquad &&f_9 = f_8 + f7 = 21 + 13 = 34 \\
&f{10} = f_9 + f8 = 34 + 21 = 55 \qquad &&f{11} = f_{10} + f_9 = 55 + 34 = \underline{\underline{89}} \\
\end{align}$$
### b)
Da wir annehmen können, dass die Folge konvergiert. Können wir davon ausgehen, dass die Folge gegen $1$ konvergiert.

## Aufgabe 3
1.  Da $(a_n)$ und $(b_n)$ nach Voraussetzung konvergieren, sind beide Folgen beschränkt, es gibt also $K_a,K_b > 0$, sodass $|a_n|\leq K_a$ und $|b_n|\leq K_b$ für alle $n$. Wir wählen $K=max{K_a,K_b}$, sodass $|a_n|\leq K$ und $|b_n|\leq K$ für alle $n$ gilt. Wegen der Konvergenz beider Folgen gibt es zu jedem vorgegebenen $\epsilon > 0$ natürliche Zahlen $N_a$ und $N_b$, sodass: $|a_n-a|<{\epsilon \over 2K}$ für $n \geq N_a$; $|b_n-b|<{\epsilon \over 2K}$ für $n \geq N_b$ Für $N=max{N_a,N_b}$ gilt dann nach der Dreiecksungleichung: $$\begin{align} |a_nb_n-ab| &=|a_nb_n-a_nb+a_nb-ab| \\ &=|a_n(b_n-b)+(a_n-a)b| \\ &\leq|a_n(b_n-b)+(a_n-a)b| \\ &=|a_n|\cdot|b_n-b|+|(a_n-a)|\cdot|b| \\ &< K \cdot {\epsilon \over 2K}+{\epsilon \over 2K}\cdot |b| \\ &= \epsilon \end{align}$$ Die Folgen $(a_n,b_n)$ konvergiert also und ihr Grenzwert ist $ab$.


## Aufgabe 4
### a)
$$\begin{align}
&a_n > b_n \qquad \sqrt{b+1000} - \sqrt{n} > \sqrt{n+ {n\over 1000}} - \sqrt{n}\\
\iff & \sqrt{n +1000} > \sqrt{n + {n \over 1000}}\\
\iff & n+ 1000 > n + {n \over 1000}\\
\iff & 1000000
\end{align}$$
$$\begin{align}
&\lim_{n \to \infty} a_n = 0\\
&\lim(\sqrt{n + 1000} - \sqrt{n})&=& (\sqrt{(n + 1000)^2} - \sqrt{n^2}) : (\sqrt{n+1000} + \sqrt{n})\\
&&=& (n+1000 - n) : (\sqrt{n + 1000} + \sqrt{n})\\
&&=& 1000 : (\sqrt{n+ 1000} + \sqrt{n})
\end{align}$$
-> Wenn $n \to \infty$ist $a_n = 0$

$$\begin{align}
&\lim_{n \to\infty} b_n = \infty\\
&\lim (\sqrt{n+n : 1000} - \sqrt{n}) = \sqrt{1001 : 1000 -\cdot n}) - \sqrt{n} = \sqrt{1001 : 1000 -1} - \sqrt{n}\\
& = {1\over 1000} \cdot \sqrt{n} \\
\end{align}$$
-> Wenn $n\to \infty$ ist  $b_n = \infty$
### b)
