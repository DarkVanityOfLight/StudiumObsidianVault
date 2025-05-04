# $2^{O(f(n))}$

$2^{O(f(n))}$ describes **exponential growth** where the exponent is bounded by a function $f(n)$.
Formally:
- $g(n) = 2^{O(f(n))}$ means that there exist constants $c, d > 0$ such that
  $$
  g(n) \leq 2^{c \cdot f(n)}
  $$
for all sufficiently large $n$.

**Example**:
- $g(n) = 2^{3n}$ is in $2^{O(n)}$.

**Intuition**:  
This kind of growth shows up in complexity classes like [[EXPTIME]].

---

## Related
- [[EXPTIME]]
