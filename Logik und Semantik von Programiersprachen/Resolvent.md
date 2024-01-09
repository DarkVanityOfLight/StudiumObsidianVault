Seien $C_1$ und $C_2$ [Kollidierende Literal Klauseln](Kollidierende%20Klauseln.md). Ein __Resolvent__ von $C_1$ und $C_2$ ist eine Klausel der folgenden Art: 
$$(C_1 \theta \setminus D_1\theta) \cup (C_2 \theta \setminus D_2\theta)$$

wenn sie auf $D_i \subseteq C_i$ kollidieren und $unify(D_1, \overline D_2) = \theta$ 


## Beispiel

$C_1 = \lbrace P(f(x), g(y)), Q(x, y)\rbrace$
$C_2 = \lbrace \neg P(f(f(a)), g(z)), Q(f(a), z)$

Der Resolvent aus $C_1, C_2$ wäre $\lbrace Q(f(a), z)$


