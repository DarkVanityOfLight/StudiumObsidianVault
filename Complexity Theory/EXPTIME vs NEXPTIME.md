---
aliases:
  - padding argument
---

If $EXPTIME \not = NEXPTIME$ then $P \not = NP$.

__Proof__
We use a padding argument.
We proof $P = NP \implies EXPTIME = NEXPTIME$ 

Let $L \in NTIME(2^{p(n)})$ for some polynomial $p(n)$, and let $M$ be a nondeterministic $2^{p(n)}$ time bounded [TM](Turing%20Machines.md) for $L$.

Define the padded version
$$L_{pad} = \lbrace \langle x, 1^{2^{p(x)}}\rangle | x\in L \rbrace$$

$L_{pad} \in NP$: First we check whether the input $y$ is of the form $\langle x, 1^{2^{p(n)}}\rangle$, for some $x$ in poly$(|y|)$-time.

Then simulate $M$ on $x$ for $2^{p(|x|)}$ many steps and copy the output. Then the running time is _polynomial_ in $|y|$.
$L_{pad} \in P$

$L \in EXPTIME$: To check whether $x\in L$, pad $x$ with $1^{2^{p(|x|)}}$ (exptime) and run the polytime TM for $L_{pad}$.
The running time is polynomial in $|\langle x, 1^{2^{p(n)}}\rangle|$ and exponential in $|x|$.

