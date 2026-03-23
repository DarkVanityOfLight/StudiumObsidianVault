---
aliases:
  - semilinear
---
A [set](Mengen.md) $L\subseteq \mathbb Z^d$ is _linear_ if there is a base vector $\mathbf b\in \mathbb Z^d$ and a finite set of period vectors $P = \{\mathbf p_1, \dots, \mathbf p_k\}\subseteq \mathbb Z^d$ such that $$ L = L(\mathbf b, P) := \{\mathbf b + \lambda_1 p_1 + \dots + \lambda_k \mathbf p_k | \lambda_1, \dots, \lambda_k\in\mathbb N\}$$ A set $S \subseteq \mathbb Z^d$ is _semilinear_ if it is a finite union of linear sets. We define linear and semilinear sets, by the base and period vectors(not unique). Let $\mathbf b\in\mathbb Z^d$ and view $P = \{\mathbf p_1, \dots,\mathbf p_k\} \subseteq \mathbb Z^d$ as a matrix in $\mathbb Z^{d\times k}$. Then we can write $$L(\mathbf b, P) = \{\mathbf b + P\mathbf\lambda | \lambda \in \mathbb N^{k\times 1}\}$$ A set $S\subseteq \mathbb Z^d$ is [Presburger](Presburger%20Arithmetic%20is%20decidable.md) definable iff it is semiliniear. Semilinear -> Presburger. Consider a linear set $L(\mathbf b, P)$ where $\mathbf b\in\mathbb Z^d$ and $P = \{\mathbf p_1, \dots, \mathbf p_k\}\subseteq \mathbb Z^d$. Then $L(\mathbf b, P)$ is defined by the Presburger formula $$\varphi(\mathbf x) = \exists(\lambda_1, \dots, \lambda_k) \in\mathbb N^k : \mathbf x = \mathbf b + \sum^k_{i=1} \lambda_i \mathbf p_i$$ where $\mathbf x = \mathbf b = \sum^k_{i=1} \lambda_i \mathbf p_i$ is a conjunction of $d$ linear equations. Hence all semilinear sets are Presburger definable. 
Presburger -> Semilinear.
Let $A\in\mathbb Z^{k\times d}, \mathbf c\in\mathbb Z^k$. Then $S = \{\mathbf x \in\mathbb N^d | A\mathbf x = \mathbf c\}$ is semilinear. Define $S_0 = \{\mathbf x \in\mathbb N^d \setminus \{\mathbf 0 \} | Ax = \mathbf 0\}$. Let $B$ be the set of minimal elements of $S$. 
Let $P$ be the set of minimal elements of $S_0$. Then $P$ and $B$ are finite since $(\mathbb N^d, \le)$ is a [WQO](Well-quasi-ordering.md).
$S_0 = L(\mathbf 0, P)$. $\supseteq$ is trivial, for $\subseteq$, let $\mathbf s\in S_0$.
By induction with respect to $(\mathbb N^d, \le)$: Write $\mathbf s = \mathbf s_0 +\mathbf x$ for some $\mathbf s_0 \in P$. Then $A\mathbf x = A\mathbf s_0 - A\mathbf s = \mathbf 0$, hence $\mathbf x\in S_0$.
By induction $\mathbf x \in L(\mathbf 0, P)$, hence $\mathbf s = \mathbf s_0 + \mathbf x \in L(\mathbf 0, P)$.

$S = \bigcup_{\mathbf b\in B} L(b, P)$ $\supseteq$ again is clear.
For $\mathbf s \in S$, write $\mathbf s = \mathbf b+ \mathbf x$ for some $\mathbf b\in B$. Then $A\mathbf x = A\mathbf s - A\mathbf b =\mathbf 0$, thus $\mathbf x\in S_0 = L(0, P)$ and $\mathbf s = \mathbf b +\mathbf x\in L(\mathbf b, P)$.

We compute $P$ and $B$ by defining them in Presburger and computing an automata for them.
The largest absolute value of vectors in $P$ and $B$ is at most $(d+1)(||A|| + ||\mathbf c|| + 1)^k$ where $||\cdot||$ returns the maximum absolute value. 

Let $\varphi$ be a PA formula, we can assume that $\varphi$ is quantifier free, since semilinear sets are closed under finite union we may assume that $\varphi$ is a conjunction of atoms.

Observe that $\varphi$ is equivalent to a formula of the form $\exists\mathbf y. A(\mathbf x, \mathbf y) = \mathbf c$ for some matrix $A\in\mathbb Z^{k\times d}$ and $\mathbf c \in\mathbb Z^k$ 
- Replace $\langle \mathbf u, \mathbf x\rangle \ge a$ with $\exists y. \langle \mathbf u, \mathbf x\rangle - y = a$ 
- Replace $a | \langle \mathbf u, \mathbf x\rangle \ge a$ with $\exists y, z. \langle \mathbf u, \mathbf x\rangle - ay + az = 0$ 

The projection of semilinear sets is effectively semilinear, hence by our lemma, the formula $\exists\mathbf y. A(\mathbf x, \mathbf y) = \mathbf c$ defines an effectively semilinear set.