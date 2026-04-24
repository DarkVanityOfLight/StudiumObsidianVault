Let $F$ be a [pseudo-boolean](AlgoSAT/Cutting%20Planes.md) fromula and let $C$ be a constraint not yet in $F$.
A _substitution_ $\omega$ maps variables to literals or truth value.

$C$ is _substitution-redundant_ with respect to $F$ under witness $\omega$ if:
$$F \land\neg C \vDash (F\land C)\uparrow \omega$$

If $\alpha$ satisfies $F$ but not $C$, then $\alpha \circ \omega$ satisfies $F\land C$.

## Reification

Suppose we want to add the constraints
$$C_1: 3\overline a + 3x + 2y + z + w \ge 3 \quad C_2: 5a + 3\overline x + 2\overline y + \overline z + \overline w \ge 5$$
using the substitution condition.

1. We add $C_1: F \land \neg C_1 \vDash F\land C \uparrow_{\omega_ 0}$ with $\omega_0 := \{a\mapsto 0\}$. This follows since $F$ is untouched, and $C_1$ is satisfied by $\omega_0$
2. Next we add $C_2: F\land C_1 \land \neg C_2 \vDash (F \land C_1 \land C_2)\uparrow_{\omega_1}$ with $\omega_1 := \{a\mapsto 1\}$. This follows since $F$ is untouched, and $C_2$ is satisfied by $\omega_1$. $\neg C_2$ forces $3\overline x + 2\overline y + \overline z + \overline w \le 4$ which is the same as $3x + 2y + z + w \ge 3$.


