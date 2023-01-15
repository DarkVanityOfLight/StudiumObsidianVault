
Es gilt:
$f^{-1}(f(m)) = m \forall m\in M$
$f(f^{-1}(n)) = n \forall n\in N$

Komposition von [Abbildungen](Abbildungen.md) #übung 

---

Zeige $g$ eindeutig durch $g \circ f = id_M, f\circ g = id_N$ bestimmt
Sei $h: N \to M$ mit $h \circ f = id_M, f\circ h = id_N$
$\implies h = h\circ id_N = h \circ f \circ g = \underbrace{h \circ f}_{id_M} \circ g = g \square$
insbesondere $g= f^{-1}$

---

$id_m: M\to M, m \mapsto m$
$f: M \to N bij \implies f^-1 \circ f = id_M, f \circ f = id_N$

---

Warteschlangen: Bei rear hinten = vorne
Invariante: Immer eingehalten,
vorne > hinten



---


To prove this, we will use the geometric sum formula. The formula states that for any complex number $z$ such that $|z| = 1$, the sum of the first $n$ powers of $z$ is given by

$$ \sum^{n-1}_{k=0} z^k = \frac{1 - z^n}{1 - z} $$

In our case, we have $z = e^{i {2\pi \over n}}$, so

$$ \begin{aligned} \sum^{n-1}_{k=0} e^{i {2\pi k \over n}} &= \frac{1 - e^{i {2\pi n \over n}}}{1 - e^{i {2\pi \over n}}} \ &= \frac{1 - e^{i {2\pi }}}{1 - e^{i {2\pi \over n}}} \ &= \frac{1 - 1}{1 - e^{i {2\pi \over n}}} \ &= 0 \end{aligned} $$

Therefore, we have proven that for all $n \in \mathbb N$,

$$ \sum^{n-1}_{k=0} e^{i {2\pi k \over n}} = 0 $$

as desired.

---

$$\begin{align}
&f(x) = \frac{1}{3} x^5 - 2x^2\\
&0 = \frac{1}{3} x^5 - 2x^2\\
&0 = x^2 \cdot (\frac{1}{3} x^3 - 2)\\
&(x_1)^2 = 0 \iff x_1 = 0\\
& \frac{1}{3} x^3 - 2= 0\\
& \frac{1}{3} x^3 =2\\
&x^3 = 6\\
&\sqrt[3]{x^3} = \sqrt[3]{6}\\
& x_2 \approx 1.8171 \quad x_3 \approx - 1.8171

\end{align}$$
