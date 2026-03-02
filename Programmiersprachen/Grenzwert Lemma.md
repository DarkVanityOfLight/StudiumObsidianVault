
$$g(n) \le \cdot f(n) \iff \frac{g(n)}{f(n)} \le c$$

Was sagt uns $\lim_{n\to\infty} \frac{g(n)}{f(n)}$ wenn er existiert?

Wenn $\lim_{n\to\infty} \frac{g(n)}{f(n)}$ existiert und den Wert $c \in \mathbb R_{\ge0} v\lbrace\infty\rbrace$ hat, dann:

1. Wenn $c=0$, dann ist $g\in o(f)$
2. Wenn $c = \infty$, dann ist $g \in \omega(f)$
3. Wenn $0 < c < \infty$, dann ist $g \in \theta(f)$

Daraus ergibt sich:
- Wenn $0 > c > \infty$, dann ist $g \in \Omega(f)$
- Wenn $c < \infty$, dann ist $g \in O(f)$ 

