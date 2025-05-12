---
aliases:
  - appropiate
  - hard
  - complete
---


A function $f: \Sigma^{*} \to \Omega^{*}$ is a (many-one) reduction from $A\subseteq \Sigma^{*}$ to $B\in \Omega^{*}$ if for all $x\in\Sigma^*$ 
$$x \in A \iff f(x) \in B$$

Let $\mathcal F$ be a set of functions called notion of reducibility.
We say $A$ is $\mathcal F$ reducible to $B$ ($A \le_\mathcal F  B$) if there exists a reduction $f\in \mathcal F$ from $A$ to $B$.

---
## Hardness and Completeness

Let $C$ be a [complexity class](Complexity%20Classes.md) and $\mathcal F$ be a set of functions.

- A problem $B$ is $C$-__hard__ under $\mathcal F$ if all $A\in C$ are $\mathcal F$ reducible to $B$
- A problem $B$ is $C$-__complete__ under $\mathcal F$ if $B\in C$ and $B$ is $C$-hard

Two notions of reducibility:
- $\le_p$: polynomial-time reducibility
- $\le_{log}$ logspace reducibility (given by $\mathcal F = \lbrace \text{logspace computable functions}\rbrace$)

$\mathcal F$ is __appropiate__ for a class complexity class $C$ if:
- $F$ is closed under composition $(f, g \in\mathcal F \implies g\circ f \in \mathcal F)$
- $C$ is closed under $\mathcal F$ (if $L\in C$ and $K \le_\mathcal F L$ then $K\in C$)

