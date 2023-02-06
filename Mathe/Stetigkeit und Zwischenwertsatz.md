

## Notation
Sei $f: D\to\mathbb R$ eine Funktion und $a\in D$. Gilt für jede Folge $(x_{n})$ in $D$ mit

$$\lim_{n\to\infty} x_{n} = a$$
dass

$$\lim_{n\to\infty} f(x_{n}) = c$$
(also insbesondere, dass $lim_{n\to\infty}f(x_{n})$ existiert) dann schreibe
$$\lim_{x\to a}f(x) = c$$
Betrachten wir nur Folgen mit $x_{n} < a$ so schreiben wir
$$\lim_{\begin{matrix} &x\to a \\ &x<a\end{matrix}} f(x) = c$$
analog für $>$ und $\not =$

## Stetigkeit

Eine Funktion $f: D\to\mathbb R$ heißt __stetig__ in $a\in D$, wenn

$$\lim_{x\to a} f(x) = f(a)$$


Sind $f: D\to\mathbb R$ und $g: D\to\mathbb R$ stetig, so auch
$$f+g: D\to\mathbb R, x\mapsto f(x) + g(x)$$
und

$$f\cdot g: D\to\mathbb R, x\mapsto f(x) \cdot g(x)$$

Ist $f(x) \not = 0\forall x\in D$, so ist auch
$$\frac{1}{f}:D\to\mathbb R, x\mapsto \frac{1}{f(x)}$$
stetig. Sind $f: D\to\mathbb R$ und $g: E\to\mathbb R$ stetig mit $f(D)\subset E$ dann ist auch die [Komposition](Komposition.md)
$$g\circ f: D\to\mathbb R, x\mapsto g(f(x))$$
stetig.
