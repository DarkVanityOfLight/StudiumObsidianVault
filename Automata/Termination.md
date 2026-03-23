Let $S = (\Gamma, \gamma_0, \to)$ be a [Transition System](Transition%20System.md). An _infinite run_ is an infinite sequence $\gamma_0, \gamma_1, \gamma_2, \dots\in\Gamma$ of configurations with 
$$\gamma_0 \to \gamma_1 \to \gamma_2 \to \dots$$
We say $S$ _terminates_ if it has no infinite run.


> [!DEFINITION]
> For $\gamma\in \Gamma$, let 
> $post(\gamma) = \{\gamma' \in\Gamma | \gamma \to \gamma'\}$
> $post^*(\gamma) = \{\gamma' \in\Gamma | \gamma \to^*\gamma'\}$
> We say that the transition system is _finitely branching_ if for every $\gamma\in\Gamma$, the set $pos(\gamma)$ is finite.


Let $W = (\Gamma, \gamma_0, \to, \le)$ be a finitely branching [WSTS](Well-structured%20transition%20systems.md) such that 
- $\le$ is decidable
- Given $\gamma \in\Gamma$, we can compute $post(\Gamma)$
Then the termination problem for $W$ is decidable.

> [!LEMMA]
> Let $S = (\Gamma, \gamma_0, \to)$ be a finitely branching transition system. If $S$ is terminating, then $post^*(\gamma_0)$ is finite.

Suppose $S$ is finitely branching and terminating. Towards a contradiction, suppose $post^*(\gamma_0)$ is infinite.
Consider the following tree:
1. Create a root node and label it with $\gamma_0$
2. Create child nodes as follows: For each node labeled with $\gamma$, add a new child for each $\gamma'$ with $\gamma \to\gamma'$
Since $S$ is finitely branching, the tree is locally finite, since $post^*(\gamma_0)$ is infinite, the tree is infinite. By [Koenigs Lemma](Koenigs%20Lemma.md), it has an infinite branch, the branch yields an infinite run which is a contradiction.

> [!DEFINTION]
> A run $\gamma_0 \to \gamma_1 \to \gamma_2 \to \dots \to \gamma_n$ is called self-covering if $\gamma_i \le \gamma_n$ for some $i\in[0, n-1]$

A WSTS has an infinite run if and only if it has a self covering run.

Suppose $\gamma_0 \to \gamma_1 \to \gamma_2 \dots$ is an infinite run. Since $\le$ is a [WQO](Well-quasi-ordering.md), there are $i, j$ with $i < j$ such that $\gamma_i \le \gamma_j$. Hence $\gamma_0 \to \gamma_1 \to \dots \to \gamma_j$ is a self-covering run.
Conversely suppose $\gamma_0\to\gamma_1 \to \dots\to\gamma_n$ is a self-covering run with $\gamma_i \le \gamma_n$, by the compatibility of runs, there is a new run from $\gamma_n$ landing in larger configurations, this can be repeated.

We are now ready to check termination. We work with trees whose nodes are labeled with configurations from $\Gamma$. For a node $v$, let $\gamma_v \in\Gamma$ be its label. A node on a path from the root to $v$ is called ancestor of $v$.

```
Init t as tree with one node, labled by gamma_r
while t has a leaf v with post(gamma_v) != empty
	take a leaf v with post(gamma_v) != empty
	for gamma' in post(gamma_v) do
		add a child under v with label gamma'
		if v has an ancestor notv with gamma_notv <= gamma'
			return non terminating
return terminating
```

The algorithm must terminate, suppose it doesn't. The algorithm constructs an infinite tree that is locally finite. By [Koenigs Lemma](Koenigs%20Lemma.md), the tree must have an infinite branch $v_0 \to v_1 \to v_2 \to\dots$. Since $\le$ is a [WQO](Well-quasi-ordering.md), there must be nodes $v_i$ and $v_j$, $i<j$, such that $\gamma_{v_i} \le \gamma_{v_j}$, but then the algorithm would have reported non-terminating when adding $v_j$.

