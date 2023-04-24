
Alle Funktionen die maximal so stark wachsen wie $f$
$$O(f) = \lbrace g: \mathbb N \to \mathbb R_{\ge0} | \exists c > 0 \exists n_{0} \in\mathbb N \forall n \ge n_{0} : g(n) \leq f(n)\rbrace$$
$g\in O(f)$ bedeutet: $g$ wächst asymptotisch höchstens so schnell wie $f$


Alle Funktionen die Mindestens so stark wachsen wie $f$:
$$\Omega(f) := \lbrace g: \mathbb N \to \mathbb R_{\ge0} | \exists c >0 \exists n_{0} \in\mathbb N \forall n\ge n_{0}: g(n) \ge c \cdot f(n)\rbrace$$
$g\in\Omega(f)$ bedeutet $g$ wächst asymptotisch mindestens so schnell wie $f$

Die Schnittmenge der beiden:
$$\theta(f) = O(f) \cap \Omega(f)$$
$g\in \theta(f)$ bedeutet $g$ wächst asymptotisch genauso schnell wie $f$


Alle Funktionen die strikt langsamer wachsen:
$$o(f) := \lbrace g: \mathbb N \to \mathbb R_{\ge0} | \forall c > 0 \exists n_{0} \in \mathbb N \forall n \ge n_{0}: g(n) \le c\cdot f(n)\rbrace$$

Alle Funktionen die strikt schneller wachsen:
$$\omega(f) := \lbrace g: \mathbb N \to \mathbb R_{\ge0} | \forall c > 0 \exists n_{0} \in \mathbb N \forall n \ge n_{0}: g(n) \ge c\cdot f(n)\rbrace$$


#wichtig

## Beispiel

$$n \in o(n^2)$$
### Beweis 
Wir müssen yeigen: $\forall c > 0 \exists n_{0} \in\mathbb N \forall n\ge n_{0}: n \le c  \cdot n^2$
Sei also $c > 0$ beliebig. WIr setzen $n_{0}$ so, dass $n_{0} \ge \frac{1}{c}$.
Dann gilt für alle $n \ge n_{0}$:

$$\begin{align*}
n &\ge n_{0} &\ge \frac{1}{c} \text{ und somit } c \cdot n^{2} &= (c\cdot n) \cdot n &\ge n \\
\iff c\cdot n &\ge 1
\end{align*}$$

Umgekehrt gilt:

$$n^{2}\in \omega(n)$$

## Eigenschaften

Für alle Funktionen $f, g, h : \mathbb N \to \mathbb R_{\ge 0}$ gilt

1. $f \in O(f), f \in \theta(f), f \in \Omega(f)$
2. $f\not \in o(f), f \not \in \omega(f)$
3. Wenn $f\in O(g)$ und $g \in O(h)$, dann $f\in O(h)$
4. $f\in O(g) \iff g\in \Omega(f)$
5. $f\in o(g) \iff g \in \omega(f)$
6. $f\in \theta(g) \iff g \in \theta(f)$
7. Für jede Konstante $c \in \mathbb R_{>0}$ ist $O(c\cdot f) = O(f)$
8. $O(f) + O(g) = O(f+g) = O(\max\lbrace f, g\rbrace)$
9. $O(f) \cdot O(g) = O(f\cdot g)$



