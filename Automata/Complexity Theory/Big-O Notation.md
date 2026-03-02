Big-O ($O(f(n))$) describes an **upper bound** on the growth rate of a function.

Formally:
- $f(n) = O(g(n))$ means there are constants $c > 0$ and $n_0$ such that
  $$
  \forall n \geq n_0, \quad f(n) \leq c \cdot g(n)
  $$

**Intuition**:  
Big-O tells you that $f(n)$ doesn't grow faster than $g(n)$ (up to constant factors) for large enough $n$.

---

## See also
- [[Big-Omega Notation]]
- [[Little-o Notation]]
