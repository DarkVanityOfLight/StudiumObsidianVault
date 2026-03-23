If $(X, \le)$ is a [WQO](Well-quasi-ordering.md), $(X^\omega, \le_\omega)$ is not a WQO. This is in contrast to [Embedding finite sequences](Embedding%20finite%20sequences.md).

## Rado's Ordering

We define following ordering on $R = \{(i, j) \in \mathbb N^2 | i < j\}$
$$(i, j) \le^R (k, \ell) \iff (i = k \land j \le \ell) \lor i, j \le k$$
then $(R, \le^R)$ is a WQO.

Let $(i_1, j_1), (i_2, j_2), \dots$ be an infinite sequence, suppose $i_1, i_2, \dots$ is bounded that is there is $B\in \mathbb N$ with $i_k \le B$ for every $k\in \mathbb N$. Then we can pick an infinite subsequence $(i, j'_1), (i, j_2'), \dots$, again we can pick an infinite subsequence $(i, j_1''), (i, j''_2),\dots$ where $j_1'' \le j_2'' \le \dots$ since $(\mathbb N, \le)$ is a WQO. But then $(i, j_1''), (i, j_2''), \dots$ is also an infinite ascending chain with respect to $\le^R$.

Suppose $i_1, i_2, \dots$ is unbounded, that is for every $B\in \mathbb N$, there is a $k\in \mathbb N$ with $i_k > B$. Then in particular, there is a $k\in\mathbb N$ with $i_1 < i_k$ and $j_1 < i_k$. Thus $(i_1, j_1) \le^R (i_k, j_k)$.

But $(R^\omega, \le_\omega^R)$ is not a WQO.
Consider the sequence
$$\begin{align}
\sigma_1 = & ((1, 2), (1, 3), (1, 4), \dots)\\
\sigma_2 = & ((2, 3), (2, 4), (2, 5), \dots)\\
\sigma_3 = & ((3, 4), (3, 5), (3, 6), \dots)\\
\vdots\\
\sigma_i = &((i, i+1), (i, i+2), (i, i+3))\\
\vdots
\end{align}$$
Then $\sigma_i \not\le^R_\omega$ for $i < j$, the element $(i, j+1)$ cannot embed into any element of $\sigma_j = ((j, j+1), (j, j+2), \dots)$.

