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

