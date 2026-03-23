The Ackermann [function](Mathe/Funktionen.md) $A: \mathbb N^2 \to\mathbb N$ is defined as follows

- $A(0, n) = n+1$
- $A(m+1, 0) = A(m, 1) \quad A(m+1, n+1) = A(m, A(m+1, n))$


The Ackermann function is not [primitive recursive](Primitive%20Recursive%20functions.md), intuitively to construct a primitve recursive function that grows fast, we can take a function $f: \mathbb N \to\mathbb N$ and iterate $f': \mathbb N \to \mathbb N$ with $f'(n) = f^n(1)$, for each primitive recursive function, this can be repeated a bounded number of times, the Ackermann function repeats the "iteration process" as often as the input specifies.

> See [Majorantenkriterium](Konvergenzkriterien.md#Majorantenkriterium) 
> For $\mathbf u\in\mathbb N^k, \mathbf u = (u_1, \dots, u_k)$ let $|\mathbf u| = \max\{u_1, \dots, u_k\}$. We say that a function $f: \mathbb N^k \to\mathbb N$ is _majorized_ by $g: \mathbb N\to\mathbb N$  if $f(\mathbf u) < g(|\mathbf u|)$ for every $\mathbf u\in\mathbb N^k$.


For every primitive recursive function $f$, there exists an $m\in\mathbb N$ such that $f$ is majorized by $A_m$.
Intuitively the $m$ is the nesting depth, this implies that $A$ cannot be primitive recursive, otherwise $A$ would be majorized by some $A_m$. But then $A(m, m) < A_m(m) = A(m, m)$ which is a contradiction.

We now can use structural induction:
1. Zero $z(n) = 0 < n+1 = A_0(n)$ 
2. Successor: $s(n) = n+1 < n+2 = A_1(n)$
3. Projections: For $\mathbf u = (u_1, \dots, u_k)$, we have $$\pi^k_\ell (\mathbf u) = u_\ell < |\mathbf u| + 1 = A_0(|\mathbf u|)$$
4. Composition, suppose $g_1, \dots, g_\ell: \mathbb N^m \to\mathbb N$ and $h:\mathbb N^\ell \to \mathbb N$ are majorized by $A_{r_1}, \dots, A_{r_\ell}$ and $A_s$. Consider $f(\mathbf u) = h(g_1(\mathbf u), \dots, g_\ell(\mathbf u))$. For $\mathbf u\in\mathbb N^m$, choose $j\in [1, \ell]$ so that $g_j(\mathbf u) = \max\{g_i(\mathbf u) | i\in[1, \ell]\}.$ Then we have 
   $$f(\mathbf u) < A_s(g_j(\mathbf u)) < A_s(A_{r_j}(|\mathbf u|)) < A_{s+r_j + 2}(|\mathbf u|) \le A_{s+r+2}(|\mathbf u|).$$
   where $r = \max\{r_1, \dots, r_\ell\}$. Thus $f$ is majorized by $A_{s+r+2}$.
5. Primitive Recursion, suppose $g: \mathbb N^k \to\mathbb N$ and $h: \mathbb N^{k+2} \to \mathbb N$ and consider $f: \mathbb N^{k+1} \to \mathbb N$ with $f(\mathbf u, 0) = g(\mathbf u)$ and $f(\mathbf u, n+1) = h(\mathbf u, n, f(\mathbf u, n))$. Moreover, let $g$ and $h$ be majorized by $A_r$ and $A_s$, respectively. Take $q = 1 + \max\{r, s\}$, then 
   $$f(\mathbf u, n) < A_q(n+ |\mathbf u|) \quad\forall \mathbf u,n$$
   By induction on $n$, first $f(\mathbf u, 0) = g(\mathbf u) < A_r(|\mathbf u|) < A_q(|\mathbf u|)$, moreover
   $$f(\mathbf u, n+1) = h(\mathbf u, n, f(\mathbf u, n)) < A_s(\max\{|\mathbf u|, n, \underbrace{f(\mathbf u, n)\})}_{=: M}.$$
   We bound $M$, induction yields $f(\mathbf u, n) < A_q(n+ |\mathbf u|)$ and since $\max\{|\mathbf u|, n \le n+|\mathbf u|\} < A_q(n + |\mathbf u|)$, we have $M < A_q(n+|\mathbf u|)$. Therefore
   $$\begin{align}
   f(\mathbf u, n+1) < A_s (M) &< A_s(A_q(n+ |\mathbf u|))\\
   &\le A_{q-1}(A_q (n+|\mathbf u|)) = A_q(n+1+ |\mathbf u|).
   \end{align}$$
   This proves the claim, therefore with $t := \max\{|\mathbf u|, n\}$, we have
   $$f(\mathbf u, n) < A_{q}(n + |\mathbf u|) \le A_q(2t+3) = A_q(A_2(t)) < A_{q+4}(t).$$
   
   