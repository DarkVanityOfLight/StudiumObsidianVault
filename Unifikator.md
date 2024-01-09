Ein __Unifikator__ einer [Menge](Mengen.md) $U$ von [Literalen](Literal.md) ist eine [Substitution](Substitution.md), die alle Liteale in $U$ gleichsetzt. Hat $U$ einen Unifikator, wird es __unifizierbar__ genannt.

## Beispiel

$$U = \lbrace P(f(x), g(y)), P(f(f(a)), g(z))\rbrace$$
$$\theta_1 = \lbrace f(a)/x, a/y, a/z\rbrace$$

## Allgemeinster Unifikator

Ein __allgemeinster Unifikator(mgu)__ von $U$ ist ein Unifikator $\theta$, d