---
aliases:
  - WQO
---
A [quasi-ordering](Halbordnung.md) is a _well_-quasi-ordering(WQO) if for every infinite sequence $x_1, x_2, \dots$ in $X$ there are indices $i, j$ with $i < j$ such that $x_i \le x_j$.


Let $(X , \le)$ be a quasi-ordering. If $x_1, x_2, \dots$ is an infinite sequence
in $X$, then a _subsequence_ is a (finite or infinite) sequence of the form $x_{i1}, x_{i2}, ...$ for some indices $i_1 < i_2 < \dots$ . In other words,
$y_1, y_2, \dots$ is a subsequence of $x_1, x_2, \dots$ if it is obtained by deleting
elements.



Let $(X, \le)$ be a quasi ordering and $x_1, x_2, \dots$ be a finite or infinite sequence in $X$.
- The sequence is an _ascending chain_ if $x_i \le x_j$ for every $i, j$ with $i\le j$
- It is _strictly decreasing_ if $x_i > x_j$ for every $i, j$ with $i < j$
- A subset $Y\subseteq X$ is an _anti-chain_ if for $x, y \in Y$, $x\not= y$, we have $x \not\le y$ and $y \not\le x$.



We can give the following equivalent characterizations for WQOs

1. $(X, \le)$ is a WQO
2. Every infinite sequence in $X$ has an infinite ascending chain as subsequence
3. $(X, \le)$ has no infinite decreasing chain and no infinite anti-chain
4. For every non empty [upwards closed](Upwards%20Closed.md) $U \subseteq X$, there is a finite subset $U_0 \subseteq U$ such that $U_0\uparrow = U$.


$(1) \implies (2)$
Let $x_1, x_2, ...$ be an infinite sequence of $X$.
$i\in \mathbb N$ is dominated if there is $j > i$, with $x_i \le x_j$, otherwise $i$ is undominated.

Let $U \subseteq \mathbb N$ be the set of undominated indices.

$U$ is _finite_:
If $U$ is infinite, then let $U = \lbrace i_1, i_2, \dots\rbrace$ with $i_1 < i_2 < \dots$
Since $(X, \le)$ is a WQO, the infinite sequence $x_{i_1}, x_{i_2}, \dots$ in $X$ must have $k, l$ with $k < l$ and $x_{i_k} \le x_{i_l}$, but then $i_k$ is dominated, which is a contradiction.

Since $U$ is finite, let $M = \max U$ the largest indices in $U$, then every indice $n > M$ is dominated and we can construct the subsequence $x_{i_1}', x_{i_2}', \dots$ as follows:

Set $i'_1 = M + 1$, for every position $k$ we have $i_k' > M$, and thus $i'_k$ is dominated, so there must be a $j > i_k'$ with $x_{i'_k}$ and thus set $i'_{k+1} = j$.

$(2) \implies (3)$

Suppose $(X, \le)$ has an infinite strictly decreasing chain, $x_1, x_2, x_3 > ...$, then this exact sequence clearly has no infinite ascending chain as a subsequence, which is a contradiction.

Suppose $(X, \le)$ has an infinite antichain $A \subseteq X$, consider a sequence $x_1, x_2, \dots$ of pairwise distinct elements of $A$. Since this sequence has an infinite ascending chain as a subsequence, there must be $i < j$ with $x_i \le x_j$.

$(3) \implies (4)$

First we notice that every nonempty subset $U \subseteq X$ has a minimal element. Towards a contradiction this was not the case, then for any $x_1 \in U$, there is $x_2 \le x_1$, inductively we construct $x_1 > x_2 > x_3$ which is a contradicition.

Now let $U \subseteq X$  be any nonempty upward closed set and let $x_1$ be the minimal element of $U$. Consider $U_1 \setminus x_1 \uparrow$. If $U_1$ is empty we are done. Otherwise there is $x_2 \in U_1$ which is minimal and note that $x_1 \not\le x_2$ and $x_2 \not\le x_1$. Inductively we can build a sequence $x_1, x_2, ...$. This sequence is an anti-chain and by assumption, not infinite. So $U_0 = \lbrace x_1, x_2, \dots \rbrace$ is a finite set with $U = U_0\uparrow$.

$(4) \implies (1)$
Let $x_1, x_2, ...$ be an infinite sequence. Define
$$U = \lbrace x_1, x_2, ...\rbrace\uparrow$$
$U$ is upward closed, so there exists a finite $U_0 \subseteq U$ with $U = U_0 \uparrow$, since $U_0$ is finite, there must be a $k\in\mathbb N$ with $U_0\subseteq \lbrace x_1, \dots, x_k\rbrace\uparrow$. Consider the element $x_{k+1}$, it belongs to $U$ and thus $x_{k+1} \in U_0\uparrow \subseteq \lbrace x_1, \dots, x_k\rbrace\uparrow\uparrow = \lbrace x_1, \dots, x_k \rbrace\uparrow$, therefore we have $x_i \le x_{k+1}$ for some $i\in \lbrace 1, ..., k\rbrace$, thus $(X, \le)$ is a WQO.


---


If $X \subseteq \mathbb N^k$ is an upward closed subset with $X \not= \emptyset$, then there is a
finite subset $X_0 \subseteq X$ with $X = X_0\uparrow$.
Since WQO are closed under products and $(\mathbb N, \le)$ is a WQO we know that $(\mathbb N^K, \le)$ is a WQO, the statement then follows from the last WQO characterization:
Every non-empty upward closed subset $U$ is the upward closure of a finite subset $U_0 \subseteq U$.

---

Let $S\subseteq \mathbb N$ such that $k \in \mathbb N\setminus \lbrace 0 \rbrace$, 
$$S + k \subseteq S$$
Then $S$ is ultimately periodic.

We define the relation $\le_k$ on $\mathbb N$ by
$$ n\le_k m \iff n \le m \land n \equiv m \mod k $$
$(\mathbb N, \le_k)$ is a WQO.

Assume $n\in S$ and $n \le_k m$, then
$$m = n + \ell k$$
for some $\ell \in \mathbb N$.
Since $S + k \subseteq S$, repeated applications yields $m \in S$.
Thus $S$ is upward closed with respect to $\le_k$
Because $(\mathbb N, \le_k)$ is a WQO and $S$ is upward closed, there exists a finite set $S_0 \subseteq S$ with
$$ S = S_0\uparrow $$

Define $M := \max S_0$ with respect to $\le$

For all $n \ge M$,
$$ n\in S \iff n+k\in S $$
For the forward direction, if $n\in S$, then
$$n+ k \in S + k \subseteq S$$
In the backward direction assume $n \ge M$ and $n+k \in S$, since $S = S_0\uparrow$, there is $s_0 \in S_0$ with
$$s_0 \le_k n+k$$
Thus
$$s_0 \le n+ k \land s_0 \equiv n+k \mod k.$$
Because $s_0 \le M \le n$, we obtain
$$s_0 \le n.$$
Moreover 
$$n+k \equiv n \mod k$$
so 
$$s_0 \equiv n \mod k$$
Hence $s_0 \le_k n$ and therefore $n\in S$

Then for all $n \ge M$,
$$n\in S \iff n+ k \in S$$

---

