## Kollidierende Klauseln
Seien $C_1, C_2$ Klauseln von Literalen mit paarweise verschiedenen Variablen, sie __kollidieren__, wenn eine nichtleere Teilmenge $D_i \subseteq C_i$ exisitiert, wobei 
$$unify(D_1 \cup \overline D_2) \not = fail$$

wobei $\overline D_2$ jedes Literal negiert.

### Beispiel

$$C_1 = \lbrace P(f(x), g(y)), Q(x, y) \rbrace$$
$$C_2 = \lbrace \neg P(f(f(a)), g(z)), Q(f(a), z)$$