---
aliases:
  - primitive recursive
---

Primitive recursive functions are the smallest class $PR$ of [functions](Mathe/Funktionen.md) $f: \mathbb N^k \to \mathbb N$, for $k\in \mathbb N$ that contains:

1. The zero function $z: \mathbb N\to\mathbb N, n\mapsto 0$ for $n\in\mathbb N$
2. The successor function $s: \mathbb N \to \mathbb N, n \mapsto n+1$ for $n\in \mathbb N$
3. The projections $\pi^k_{\ell}: \mathbb N^k \to\mathbb N, (x_1, \dots, x_k) \mapsto x_\ell$

and is closed under

- composition: Given $g_1, \dots, g_\ell: \mathbb N^m \to \mathbb N$ and $h: \mathbb N^\ell \to \mathbb N$, we have the function $f: \mathbb N^m \to \mathbb N$ with $f(\mathbf u) = h(g_1(\mathbf u), \dots g_\ell(\mathbf u))$ .
- Primitive Recursion: Given $g: \mathbb N^k \to \mathbb N$ and $h: \mathbb N^{k+2} \to\mathbb N$, we have $f: \mathbb N^{k+1} \to\mathbb N$ with 
  $$f(\mathbf u, 0) = g(\mathbf u), f(\mathbf u, n+1) = h(\mathbf u, n f(\mathbf u, n))$$
Intuitively Primitive recursive functions are modeled by loop programs, where the number of loop executions is known beforehand.

