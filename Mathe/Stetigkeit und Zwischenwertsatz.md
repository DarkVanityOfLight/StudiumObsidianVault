
## Notation
$f: D \to \mathbb R, \quad a \in D$
Gilt für jede Folge $(x_{n})$ in $D$ mit $\lim_{n\to\infty} x_{n}= a$, dass $\lim_{n\to\infty}f(x_{n)}= c$ mit $c \in\mathbb R$ fest.
Dann schreiben wir $\lim_{x\to a}f(x) = c$
Nur Folgen mit $x_{n}< a \quad \forall n\quad \lim_{\begin{matrix}x\to a \\ x< a\end{matrix}} f(x) = c$
Auch für  $a\not\in D$, insbesondere für $a = \pm \infty$

## Stetigkeit

$$\begin{align*}
f: & D\to\mathbb R\quad\text{stetig in $a\in D$}\\\\\\
\text{wenn} &\lim_{x\to a} f(x) = f(a)
\end{align*}$$

$$\begin{align*}
f: & D\to\mathbb R, g : D\to\mathbb R \quad\text{stetig}\\
f+ g:& D\to\mathbb R, x\mapsto f(x) + g(x)\\
&f\cdot g\\
f(x) \not = 0 \forall x\in D
\end{align*}$$

$$\begin{align*}
\frac{1}{f}:&D\to\mathbb R, x \mapsto \frac{1}{f(x)} \text{stetig}
\end{align*}$$
$$\begin{align*}
f_{\text{Stetig}}: D\to\mathbb R,\quad g:E\to\mathbb R,\quad f(D) \subset E\\
\implies g\circ f: D\to\mathbb R, x\mapsto g(f(x))\quad\text{stetig}
\end{align*}$$

$$\lim_{x\to0}\exp(x) = 1$$
