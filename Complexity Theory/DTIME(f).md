## Definition
$DTIME(f)$ is the class of languages that can be decided by a deterministic [Turing Machine](Turing%20Machines.md) within $O(f(n))$ steps, where $n$ is the size of the input.

> $$DTIME(f) = \lbrace \text{languages accepted by deterministic, $f$-time bounded TMs} \rbrace$$

Formally:
- $L \in DTIME(f)$ if there exists a deterministic TM $M$ such that:
  - For all inputs $x$, $M$ halts in at most $cf(|x|)$ steps for some constant $c$.
  - $x \in L$ if and only if $M$ accepts $x$.

## Intuition
Deterministic, time-bounded computation: the machine behaves predictably and fast (within $f(n)$ time).

## Related
- [[NTIME(f)]]
- [[DSPACE(f)]]
- [[NSPACE(f)]]
- [[P]]
