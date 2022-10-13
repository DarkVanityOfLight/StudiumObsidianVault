## Aufgabe 7.1
$$\begin{align}
&|-1^n {1\over n^2}| < \epsilon \\
\implies & |{1\over n^2}| < \epsilon \\
\implies &{1\over n^2} < \epsilon \\
\implies & \lceil n \rceil> \sqrt{1\over \epsilon}
\end{align}$$
$$|a_n-a| = |(-1)^n {1\over n^2} -0| = |{1\over n^2}| = {1\over n^2}$$
$$\begin{align}
&{1\over n^2} \leq {1\over n_\epsilon^2} < \epsilon \forall n \geq n_\epsilon \\
\iff &{1\over \sqrt{2\over \epsilon}} = {\epsilon \over 2}
\end{align}$$


## Aufgabe 7.2
a
$lim_{n \rightarrow \infty} {5n-7n^2 \over (n+1)^2 - 8n}$
$$\begin{align}
&=\lim_{n \to \infty} { {5\over n} -7 \over1+ {2\over n} + {1\over n^2} - {8\over n} } = {-7 \over1} =-7
\end{align}$$
b
$$\begin{align}
&\lim_{n\to\infty} {1 \over n^2}(n+(n-1) + (n-2)+...+1)\\
&\sum_{k=1}^n k = {n(n+1) \over 2}\\
&\lim_{n\to\infty} {1 \over n^2} \cdot {n(n+1) \over 2} = \lim_{n\to\infty}{n^2 + n \over 2n^2} = \lim_{n\to\infty} {1+{1\over n} \over 2} = {1\over 2}
\end{align}$$
## Aufgabe 7.3
a
$$
(-1)^n + (-1)^{n+1} = 0
$$
b
$a_n = n$ dann ist das inverse $1 \over a_n$ also $1\over n$ konvergent.
