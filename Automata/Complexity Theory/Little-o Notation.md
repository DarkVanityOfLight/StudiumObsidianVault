Little-o ($o(f(n))$) describes a **strict upper bound** on the growth rate of a function.

Formally:
- $f(n) = o(g(n))$ means that for every $c > 0$, there exists $n_0$ such that
  $$
  \forall n \geq n_0, \quad f(n) \leq c \cdot g(n)
  $$

**Intuition**:  
Little-o means that $f(n)$ grows **slower** than $g(n)$ — not just bounded, but *strictly* dominated by it.

---

## See also
- [[Big-O Notation]]
- [[Big-Omega Notation]]
