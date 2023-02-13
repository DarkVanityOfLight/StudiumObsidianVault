Das Konzept der [Umkehrfunktion](Umkehrfunktion.md) verallgemeinert sich wie folgt:

Sei $f: D\to\mathbb R^{n}$ mit $D\subset \mathbb R^{n}$ stetig [differenzierbar](Differenzierbarkeit%20in%20der%20Multivariaten%20Analysis.md) in $a \in D$ und
$$Df(a) \in\mathbb R^{n\times n}$$ invertierbar. Dann gibt es ein $\varepsilon > 0$, sodass
$$f: B_{\varepsilon} (a) \to f(B_{\varepsilon}(a))$$
[bijektiv](Bijektiv.md) ist, und die Umkehrfunktion $f^{-1}$ ist in $f(a)$ differenzierbar mit der Inversen
$$Df^{-1}(f(a)) = Df(a)^{-1}$$ der Ableitungsmatrix von $f$.
