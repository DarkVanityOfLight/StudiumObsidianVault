Ein __Unifikator__ einer [Menge](Mengen.md) $U$ von [Literalen](Literal.md) ist eine [Substitution](Substitution.md), die alle Literale in $U$ gleichsetzt. Hat $U$ einen Unifikator, wird es __unifizierbar__ genannt.

## Beispiel

$$U = \lbrace P(f(x), g(y)), P(f(f(a)), g(z))\rbrace$$
$$\theta_1 = \lbrace f(a)/x, a/y, a/z\rbrace$$

## Allgemeinster Unifikator

Ein __allgemeinster Unifikator(mgu)__ von $U$ ist ein Unifikator $\theta$, der ein Präfix jedes andere Unifikator $\theta'$ ist, d.h.
$$\theta' = \theta \circ \mu \text{ für ein bestimmtes }\mu$$


## Unifikationssatz

> Jede unifizierbare Literalmenge hat einen mgu

## Unifikationsalgorithmus

_Eingabe_: Eine Literalmenge $U$
_Ausgabe_: Ein mgu von $U$

1. $\theta := \emptyset$
2. Wiederhole folgendes, bis $\theta$ ein Unifikator von $U$ wird:
	1. Wähle zwei verschiedene [atomare](Logik/Atom.md) Formeln in $U\theta$ aus und finde die erste Position, bei der sie sich unterscheiden
	2. Ist keines der beiden Zeichen eine Variable, "fail".
	3. Nun unterscheiden sie sich bei Subtermen $t_1 = x$ und $t_2$, wenn $x$ in $t_2$ vorkommt, "fail"
	4. $\theta := \theta \circ [t_2 / x]$
3.  Gebe $\theta$ aus