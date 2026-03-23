Let $(X, \le)$ be a [WQO](Well-quasi-ordering.md), for any [Downward Closed](Downward%20Closed.md) subset $D \subseteq X$, there is a $n\in\mathbb N$ and ideals $I_1, \dots, I_n\subseteq X$ such that $D = I_1 \cup \dots \cup I_n$.


We first proof a lemma to decompose the set.

>[!LEMMA]
> Let $(X, \le)$ be a WQO and $D\subseteq X$ be a non-empty subset that is not an ideal. Then there are downward closed $D_1, D_2\subseteq X$ with $D = D_1 \cup D_2$ and $D_i \subsetneq D$ for $i = 1, 2$.

Because $D$ is not an ideal there is $x_1, x_2\in D$ with no common upper bound.
Consider
$$D_1 = \{ x \in D | x_1 \not\le x\} \quad D_2 = \{x \in D | x_2 \not\le x\}$$

Since $x_1$ and $x_2$ have no common upper bound in $D$, we have $D_1 \cup D_2 = D$. Also $D_1, D_2$ are downward closed and $D_i \subsetneq D$ (because $x_i \not\in D_i$) for $i=1, 2$.


We are ready to proof the main theorem.
We build a tree, where the nodes are non empty downward closed sets of $D$ and the leafs are ideals:

- The root is labeled with $D$
- We distinguish two cases
	- If all leafs are labeled with ideals stop
	- If there is a leaf labeled by some $E\subseteq X$ that is not an ideal we apply the lemma to write $E = E_1 \cup E_2$ with $E_i \subsetneq E$ for $i = 1, 2$ and add two children labeled with $E_1$ and $E_2$

In each step if $E_1, \dots E_n$ are the labels of all leaves, then $E_1 \cup \dots \cup E_n$.

Also the process has to terminate, or else by [Koenigs Lemma](Koenigs%20Lemma.md) we can construct an infinite branch, containing a infinite sequence $F_1 \supsetneq F_2 \supsetneq \dots$ of downward closed sets, which cannot exist.

If the process stops, all leaves are labeled with ideals.




