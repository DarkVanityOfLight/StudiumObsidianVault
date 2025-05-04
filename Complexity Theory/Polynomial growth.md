## $n^{O(1)}$

$n^{O(1)}$ refers to **polynomial growth**.

More precisely:
- A function $f(n)$ is in $n^{O(1)}$ if there exist constants $c, d > 0$ such that
  $$
  f(n) \leq c \cdot n^d
  $$
for all sufficiently large $n$.

**Intuition**:  
The runtime or space usage is bounded by some polynomial in the input size.

---

## Related
- [[P]]
- [[NP]]
- [[DTIME(f)]]
