
## Simple Idea

- Compute the product automata
- Explore the product automata lazily
	- Check there is no reachable pair $(p, q)$ from $(p_0, q_0)$ with $p \in F$ and $q \not\in F$ (or the converse)

> Runs in $O(|\Sigma||Q|^2)$

## Hopcroft-Karp

> [!Idea]
> Use the transitivity of the equivalence, using a union find datastructure.


Initialize the union-find datastructure
$S = \{(p_0, q_0)\}$
while $S \not = \emptyset$
	remove $(p, q) \in S$
	for $a \in \Sigma$
		$s \leftarrow \text{find}(\delta(p, a)), t \leftarrow \text{find}(\delta(q, a))$ 
		if $t \not =  s$
			$\text{union}(s, t)$
			$S \cup (s, t)$
			if $s \in F \land t\not\in F$ reject (or the symmetric condition)

_Correctness Proof Sketch_

The Algorithm generates an Equivalence Relation $\equiv_k$ in the $k$ iteration. We assume $\equiv$ eventually stabilizes. 
$\equiv$ is the finest invariant Relation on $Q$ with $p_0 \equiv q_0$.

> _Lemma_
>  $\equiv$ is finer than any invariant relation $\approx$  with $p_0 \approx q_0$

Inductively, $r \equiv_k s \implies r\approx s$, clear for $k=0$. 
$r \equiv_k s$ and $r \not\equiv_{k-1} s$, then there is $\delta(p, a) \equiv_{k-1}  r$ and $\delta(q, a) \equiv_{k-1} s$

$$ (p, q) \in S \implies p \equiv_{k-1} q \implies p \approx q \implies \delta(p, a) \approx \delta(q, a) \implies r \approx s $$
> *Lemma*
> $\equiv$ is invariant

Consider the Graph $G_k$ with vertexes $q \in Q$. $p, q\in Q$ are adjacent iff

- $(p, q) \in S$
- $\forall a. \delta(p, a) \equiv_k \delta(q, a)$

Observe via induction $p \equiv_k q \implies p, q$ are adjacent in $G_k$

If $p \equiv q$ then $p, q$ are connected in $G_m$, by a path $p = p_1, p_2, ..., p_n = q$. Since $S$ is empty at termination
$$ \delta(p, a) = \delta(p_1, a) \equiv \delta(p_2, a) \equiv ... \equiv \delta(p_n, a) = \delta(q, a)$$

Since $\equiv$ is the finest invariant Relation with $p_0 \equiv q_0$ the Algorithm is correct.

- Assume $L(p_0) = L(q_0)$ take the real Relation $E = \{ (p, q) | L(p) = L(q) \}$, $\equiv$ is finer then $E$ (since E is invariant), and thus does not relate final to non final states since $E$ doesn't.
- Conversely because $\equiv$ is invariant we obtain via induction on $w$, $\delta(p, w) \equiv \delta(q, w)$. So either $w$ is accepted by both states or rejected.
