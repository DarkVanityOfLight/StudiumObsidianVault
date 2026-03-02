Big-Omega ($\Omega(f(n))$) describes a **lower bound** on the growth rate of a function.

Formally:
- $f(n) = \Omega(g(n))$ means there are constants $c > 0$ and $n_0$ such that
  $$
  \forall n \geq n_0, \quad f(n) \geq c \cdot g(n)
  $$

**Intuition**:  
Big-Omega says that $f(n)$ eventually grows **at least** as fast as $g(n)$ (up to constant factors).

---

## See also
- [[Big-O Notation]]
- [[Little-o Notation]]
