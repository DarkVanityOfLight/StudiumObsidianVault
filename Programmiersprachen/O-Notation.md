

Für jedes $f: \mathbb N \to \mathbb R_{\geq 0}$ definieren wir

$$O(f) := \lbrace g: \mathbb N\to \mathbb R_{\geq 0} | \exists c > 0 \exists n_{0} \in \mathbb N \forall n \geq n_0 : g(n) \leq c \cdot f(n)\rbrace$$
$g$ wächst asymptotisch höchstens so schnell wie $f$


$$\Omega(f) := \lbrace g: \mathbb N \to \mathbb R_{\geq 0} | \exists c > 0 \exists n_0\in \mathbb N \forall n\geq n_0 : g(n) \geq c \cdot  f(n)\rbrace$$
$g$ wächst asymptotisch mindestens so schnell wie $f$


$$\Theta(f) := O(f) \cap \Omega(f)$$
$g$ wächst asymptotisch genauso schnell wie $f$


$$o(f) := \lbrace g: \mathbb N\to\mathbb R_{\geq 0} | \forall n\geq n_0 : g(n) < c \cdot f(n) \rbrace$$
$g$ wächst asymptotisch langsamer als $f$


$$\omega(f) := \lbrace g: \mathbb N \to \mathbb R_{\geq 0} | \forall c > 0 \exists n_0 \in\mathbb N \forall n \geq n_0 : g(n) > c \cdot f(n) \rbrace$$

$g$ wächst asymptotisch schneller als $f$

## Grenzwert Lemma

Wenn der Grenzwert $\lim_{n\to\infty} \frac{g(n)}{f(n)}$ existiert und Wert $c\in\mathbb R_{\geq 0} \cup \lbrace\infty\rbrace$ hat, dann gilt

1. Wenn $c = 0$ dann ist $g \in o(f)$
2. Wenn $c=\infty$ dann ist $g\in\omega(f)$
3. wenn $0 < c < \infty$ dann ist $g\in\Theta(f)$

Aus der Kombination der vorherigen Fälle ergibt sich

4. Wenn $0\leq c< \infty$ dann ist $g\in O(f)$
5. Wenn $0 < c \leq \infty$ dann ist $g\in\Omega(f)$

