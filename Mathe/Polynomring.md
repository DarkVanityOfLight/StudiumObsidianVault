Sei $R$ ein kommutativer [Ring](Ring.md) mit $1$. Der Polynomring $R[x]$ ueber $R$ in der Unbestimmten $x$ ist die Menge aller Ausdruecke
$$f = a_{0}x^{0} + a_{1}x^{1} +... + a_{n}x^{n}$$
mit $n\in\mathbb N_{0}, a_{i} \in R, a_{n}\not = 0$
Wir nennen $deg (f)$ den __Grad__ von $f$ und setzen $deg(0) = -\infty$.
Für $i > deg(f)$ setzen wir $a_{i} = 0$.
Addition und Multiplikation von Polynomen sind wie folgt definiert:

$$\begin{align*}
&(a_{0} x^{0}+ a_{1}x^{1} + ... + a_{n}x^{n}) + b_{0}x^{0}+ b_{1}x^{1} + ... + b_{m}x^{m}\\
&= (a_{0}+ b_{0})x^{0} + (a_{1} + b_{1}) x^{1} + ... + (a_{\max(n, m)} + b_{\max(n, m)})x^{\max(n, m)}\\
\end{align*}$$
und 

$$\begin{align*}
&(a_{0} x^{0} + a_{1} x^{1}+ ... + a_{n}x^{n}) \cdot (b_{0}x^{0}+b_{1}x^{1} + ... + b_{m} x^{m})\\
&= x_{0}x^{0} + c_{1} x^{1} + ... + c_{n+m} x^{n+m}
\end{align*}$$
wobei
$$c_{k} = \sum\limits^{k}_{j=0} a_{j} b_{k-j}$$
(sind also so gemacht, dass das [Distributivgesetz](Distributivgesetz.md) gilt). Polynomringe in mehr als einer Variable definieren wir induktiv als

$$R[x_{1}, ..., x_{r}] = R[x_{1}, ..., x_{r-1}][x_{r}]$$

Als Datenstruktur ist ein Polynom vom Grad $n$ nichts andere als eine Liste
$$a_{0}x^{0} + a_{1}x^{1}+ ... + a_{n}x^{n} = (a_{0}, ..., a_{n}) \in R^{n+1}$$

---

Ein Term ist ein Polynom der Form $a_{n} x^{n} = (0, ..., 0, a_{n})$. Jedes Polynom ist offenbar eine Summ von Termen.

Nützlich werden Polynome dadurch, dass die Rechenoperationen kompatibel mit dem Einsetzen von Werten für die Variable $x$ sind. Es spielt keine Rolle ob man erst mit Polynomen rechnet und dann Werte einsetzt oder erst einsetzt und mit diesen Werten die entsprechende Rechenoperation durchführt. Auf diese Weise kann man neue Formeln herleiten, die unabhängig von dem konkreten Wert von $x$ gültig sind.

---
 Um zu zeigen, dass die lineare Abbildung $f: \mathbb{P}_2 \rightarrow \mathbb{P}_3$ mit $f(p(x))=p'(x)+(x+1)\cdot p(x)$ ein Vektorraumhomomorphismus ist, müssen wir zeigen, dass $f$ die folgenden beiden Bedingungen erfüllt:

1.  Additivität: $f(u+v) = f(u) + f(v)$ für alle $u, v \in \mathbb{P}_2$.
2.  Homogenität: $f(\lambda u) = \lambda f(u)$ für alle $\lambda \in \mathbb{R}$ und $u \in \mathbb{P}_2$.

Seien $p(x) = ax^2 + bx + c$ und $q(x) = dx^2 + ex + f$ beliebige Polynome aus $\mathbb{P}_2$.

Dann haben wir:

1.  Additivität:

$$\begin{align*} f(p(x) + q(x)) &= f((a+d)x^2 + (b+e)x + (c+f)) \\ &= (a+d) + (b+e)x + (c+f) + x(a+d)x^2 + (a+d)x(b+e) \\ &= (a+d)x^2 + (b+e)x + (c+f) + ap'(x) + bp(x) + dp'(x) + eq(x) \\ &= p'(x) + d(x+1)x^2 + (a+b+e)(x+1)x + (c+f) + p'(x) + e(x+1)x + f(x+1) \\ &= p'(x) + q'(x) + (x+1)(p(x) + q(x)) \\ &= f(p(x)) + f(q(x)) \end{align*}$$

Daher ist $f$ additiv.

2.  Homogenität:

$$\begin{align*} f(\lambda p(x)) &= f(\lambda ax^2 + \lambda bx + \lambda c) \\ &= \lambda a + \lambda b x + \lambda c + x\lambda ax^2 + \lambda a x \cdot \lambda b \\ &= \lambda(ax^2 + bx + c) + x\lambda^2 ax^2 + \lambda^2 ax \cdot \lambda b \\ &= \lambda p'(x) + (\lambda^2 x + \lambda) p(x) \\ &= \lambda(p'(x) + (x+1)p(x)) \\ &= \lambda f(p(x)) \end{align*}$$

Daher ist $f$ homogen.
Da $f$ sowohl additiv als auch homogen ist, ist $f$ ein Vektorraumhomomorphismus.