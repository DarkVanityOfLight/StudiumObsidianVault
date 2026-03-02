---
aliases:
  - NP-Intermediate
---

If $P\not = NP$, there exists a language $L\in NP\setminus P$ that is not [NP-Complete](NP-Complete.md).

Let $h: \mathbb N\to \mathbb N$. Define the following padded version of SAT:

$$SAT_h = \lbrace \varphi01^{n^{h(n)}} |\varphi\in SAT, n=|\varphi|\rbrace$$

If $h(n) = c$, then $SAT \le_p SAT_h$(via $\varphi \mapsto \varphi 01^{|\varphi|^c}$) 
=> $SAT_h$ is NP-complete

If $h(n) = n$ then $SAT_h \in P$ ($|\varphi|$ is logarithmic in the input length)

Pick $h$ large enough so that $SAT_h$ is not NP-Complete.
but small enough so that $SAT_h\not\in P$

Let $(M_i)_{i\in \mathbb N}$ be an enumerator of all determinsitic 1-tape [TMs](Turing%20Machines.md) under the standard encoding.

$h(n)$ is the smallest number $i<\log\log n$ such that $M_i$ correctly decides whether $x\in SAT_h$ within $i\cdot |x|^i$ time, for all inputs $x\in\lbrace 0, 1\rbrace^*$ with $|x| \le \log n$.If there is no such number set $h(n) = \log \log n$.

Intuitively
- $M_1$ allows linear time $(1 \cdot |x|^1)$
- $M_2$ allows quadratic time ($2 \cdot |x|^2$)
- $M_3$ allows cubic time $(3 \cdot |x|^3)$
- ...
- $M_{\log\log n-1}$ allows ($\log \log n-1$) $|x|^{\log \log n-1}$

Notice that $h$ is well defined since the definition of $h(n)$ only depends on strings in $SAT_h$ of length $\le \log n$, and hence only depends on values $h(m)$ where $m \le \log n$

>[!OBSERVE]
>$1^n \mapsto 1^{h(n)}$ is polynomial-[time constructible](Time%20constructible.md).


1. If $SAT_h \in P$ then $h(n) = O(1)$
2. If there exists $c\in\mathbb N$ with $h(n) = c$ for infinitely many $n$ then $SAT_h \in P$


Suppose there exists a TM $M$ deciding $SAT_h$ in time $c\cdot n^{c}$. Let $i \ge c$ such that $M_i = M$. By definition of $h$ $h(n) \le i$ for all $n> 2^{2^i}$. Thus $h(n) = O(1)$.


We claim that $M_c$ solves $SAT_h$ in time $c\cdot n^c$.
Towards a contradiction assume there exists an input $x$, $|x| = n$ such that $M_c$ makes a mistake on $x$ or does not halt after $c\cdot n^c$ steps. Then for all $m > 2^n$, $h(m) \not = c$ by definition of $h$.



Now assume $P \not = NP$. We are ready to show that $SAT_h$ is NP-intermediate.


- $SAT_h \in NP:$ Check the syntax of input formula $\varphi$ in poly-time, then guess and verify a satisfying assingment
- $SAT_h \not\in P$: Suppose $SAT_h \in P$. We know $h(n) \le c$ for some constant $c$. Then $\varphi \mapsto \varphi01^{|\varphi|^{h(|\varphi|)}}$ is a poly-time reduction from SAT to $SAT_h$ ($h$ is poly time computable). Hence $SAT\in P$, contradicting $P\not = NP$
- $SAT_h$ is not NP-hard: Assume $SAT_h$ is [NP-hard](NP-Hardness.md). There exists a poly time reduction from $f$ from SAT to $SAT_h$. We can assume that every formula $\varphi$ is mapped to a string $f(\varphi) = \psi 01^{|\psi|^{h(|\psi|)}}$ since $h$ is poly-time computable. (remap to some $\psi01^{|\psi|^{h(|\psi|)}}$ where $\psi$ is unsat). Intuitively:
	- $f(\varphi)$ grows polynomially in $|\varphi|$
	- $f(\varphi)$ grows superpolynomial in $|\psi|$
	Hence  $|\psi| << |\varphi|$ and we can recurse on $\psi$.
	To be more precise: We solve SAT in polynomial time as follows. Suppose $f$ runs in time $i\cdot n^i$. Choose $n_0$ so that for all $n \ge n_0$:
	- $h(n) \ge 2\cdot i$
	- $i \cdot n^{\frac{1}{2}} < n$
	Given formula $\varphi$, compute $f(\varphi) = \psi 01^{|\psi|^{h(|\psi|)}}$ and set $n = |\varphi|$, $k = |\psi|$.
	If $n < n_0$ or $k < n_0$ we solve by brute force.
	Otherwise $n, k \ge n_0$ satisfy:
	$$k^{h(k)} < k+1+k^{h(k)} = |f(\varphi)| \le i\cdot n^i$$
	therefore 
	$$k < i\cdot n^{\frac{i}{h(k)}} < i\cdot n^{\frac{1}{2}} < n$$
	Hence, we can recurse on $\psi$


