Extended Resolution combines [Resolution](AlgoSAT/Resolution.md) with the _Extension rule_

$$\frac{x\not\in F \quad \overline x \not\in F}{(x\lor \overline a \lor \overline b) \land (\overline x \lor a) \land (\overline x \lor b)}$$
(Add $x\leftrightarrow (a\lor b)$ if $x$ is fresh)

This proof system has no known super-polynomial lower bounds.
It can prove the [PHP](PHP%20Bounds.md) efficiently.


We can prove the pigeonhole principle by induction on $n$. If $M$ is a one-to-one map from $\{0, \dots, n+1\}$ to $\{0, \dots, n\}$, then we can define a one-to-one map $M'$ from $\{0, \dots, n\}$ to $\{0, \dots, n-1\}$ with
$$
M'(i) = \begin{cases}
M(i) &\text{if } M(i) \not= n\\
M(n+1) &\text{if } M(i) = n
\end{cases}, 1\le i\le n
$$

Finally we derive that there is a one-to-one mapping from $\{1, 2\}$ to $\{2\}$.

Given the pigeonhole principle over $n+1$ pigeons and $n$ holes on variables $p_{i, j}$ corresponding to a map $M$, we use the extension rule to derive $q_{i, j}$ describing the map $M'$ above.
$$q_{i, j} \leftrightarrow (p_{i, j} \lor (p_{i, n} \land p_{n+1, j})) \text{ for } 1\le i\le n, 1\le j\le n-1$$

From these clauses and the original clauses, we can derive in $O(n^3)$ steps
- $q_{i, 1} \lor \dots \lor q_{i, n-1}$ for $1 \le i \le n-1$
- $\overline q_{i, k} \lor \overline q_{j, k}$ for $1 \le i\le n$, $1\le k\le n-1$
This is the PHP over $n$ pigeons and $n-1$ holes. We can repeat this until we arrive at
$$PHP^2_1 = \{r_{1, 1}, r_{2, 1}, \overline r_{1, 1} \lor \overline r_{2, 1}\}$$
from which the empty clause can be derived trivially.

