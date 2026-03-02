## Definition
$NSPACE(f)$ is the class of languages that can be decided by a nondeterministic Turing Machine using at most $O(f(n))$ **space**.
> $$NSPACE(f) = \lbrace \text{languages accepted by nondeterministic, $f$-space bounded TMs}\rbrace$$

Formally:
- $L \in NSPACE(f)$ if there exists a nondeterministic TM $M$ such that:
  - On any input $x$, all computation paths use at most $cf(|x|)$ tape cells for some constant $c$.
  - $x \in L$ if there is an accepting computation path.


## Intuition
Nondeterministic, space-bounded computation: the machine can explore multiple possibilities, but memory usage must stay low.

## Related
- [[DSPACE(f)]]
- [[NTIME(f)]]
- [[NL]]
- [[NPSPACE]]
