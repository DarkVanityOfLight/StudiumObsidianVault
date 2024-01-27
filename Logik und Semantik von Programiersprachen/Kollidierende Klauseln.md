
Seien $C_1, C_2$ Klauseln von [Literalen](Literal.md) mit paarweise verschiedenen Variablen, sie __kollidieren__, wenn eine nichtleere Teilmenge $D_i \subseteq C_i$ existiert, wobei 
$$unify(D_1 \cup \overline D_2) \not = fail$$

wobei $\overline D_2$ jedes Literal negiert.

### Beispiel

$$C_1 = \lbrace P(f(x), g(y)), Q(x, y) \rbrace$$
$$C_2 = \lbrace \neg P(f(f(a)), g(z)), Q(f(a), z)$$

$\theta = \lbrace f(a) / x, z/y$ ist ein mgu der ersten Literale

$C_1$ und $C_2$ kollidieren an $P(f(x))$ und $\neg P(f(f(a)))$, denn negieren wir $D_2$ erhalten wir $P(f(f(a)))$ was sich durch $\theta = \lbrace f(a)/x \rbrace$ mit $D_1$ unifizieren lässt. 