Sind zwei Lösungen $x_1$ und $x_2$ einer quadratischen Gleichung in [Normalform](Normalform.md) $x^2 + px+q = 0$ bekannt, dann gilt $$x^2 + px+q=(x-x_1) \cdot (x-x_2)$$
Ein Faktor der Form $(x-a)$, wobei a eine [reelle Zahlen](Reelle%20Zahlen.md) ist , wird als Linearfaktor bezeichnet. Die Beziehung zwischen den Koeffizienten $p$ und $q$ und den Lösungen $x_1$ und $x_2$ wird durch den Satz von Viëta beschrieben: 
$$x_1 + x_2 = -p,$$$$x_1 \cdot x_2 = q$$
## Linearfaktorzerlegung
Sei $p_n$ ein reelles Polynom vom Grad $n$ und $q_m$ ein reelles Polynom vom Grad $m$ mit $m \leq n$. Dann gibt es zwei eindeutig bestimmte Polynome $h$ vom Grad $n-m$ und $r$ mit Grad $<m$, so dass
$$p_n(x) = h(x) \cdot q_m(x) + r(x)$$
bzw.
$${p_n(x) \over q_m{x}} = h(x) + {r(x) \over q_m(x)}$$
für alle $x$ mit $q_m(x) \not = 0$
Jede unecht gebrochen rationale Funktion lässt sich zerlegen in eine Summe aus einer ganz rationalen Funktion und einer echt gebrochen-rationalen Funktion.

Sei $$p_n: C \rightarrow C, p_n(x) = \sum_{j=0}^{n} a_jx^j$$
ein komplexes Polynom vom Grad $n$.
Dann gilt:
$p_n$ lässt sich vollständig in Linearfaktorzerlegen:
$$p_n(x) = a_n(x-x_1) \cdot (x-x_2)...(x-x_n)$$
wobei $x_1,...x_n$ [komplexe](Komplexe%20Zahlen.md) Nullstellen von $p_n$ sind.

