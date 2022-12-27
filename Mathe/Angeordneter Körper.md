Ein angeordneter Körper ist ein [Körper](Körper.md) $K$ mit einer [Totalordnung](Totalordnung.md) $\leq$, die verträglich mit Addition und Multiplikation ist, das heißt für all $a, b, c \in K$ gilt
1. $a\leq b \quad \implies a+c \leq b + c$
2. $0 \leq a, 0 \leq b \quad \implies 0 \leq a \cdot b$

Wir schreiben $a\geq b$ für $b \leq a$. Außerdem schreibt man
$a < b$ für $a \leq b$ und $a \not = b$(und analog für $>$)

Ist $K$ ein angeordneter Körper und $a\in K$, dann gilt
$$a^2 \geq 0$$
Für $a \geq 0$ folg dies direkt mit Punkt (2). Für $a \leq 0$ ist $-a \geq 0$ mit Punkt (1), also mit Punkt (2) wieder $a^2 = (-a)^2 \geq 0$.
Insbesondere gilt $1 > 0$
Dies impliziert, dass die Abbildung $\mathbb Z \to K, k\mapsto k\cdot 1$ [Injektiv](Injektiv.md) ist.
Jeder angeordnete Körper enthält also $\mathbb Z$ und somit auch $\mathbb Q$.

## Betragsfunktion
Sei $K$ ein angeordneter Körper. Die Betragsfunktion $K \to K$ ist definiert durch 
$$
|x| = \left\{ x\ \text{für}\ x \geq 0 \atop -x\ \text{für}\ x < 0\right.
$$

Mit Hilfe des Absolutbetrags können wir einen symmetrischen Abstandsbegriff $|a-b|$
für zwei Elemente $a, b \in K$ einführen.

## Beispiel
$$
{1\over3} \leq {1\over 2} \implies {4\over 3} \leq {3\over 2}
$$
