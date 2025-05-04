## Definition
$DSPACE(f)$ is the class of languages that can be decided by a deterministic Turing Machine using at most $O(f(n))$ **space** on its work tapes.

> $$DSPACE(f) = \lbrace \text{languages accepted by deterministic, $f$-space bounded TMs} \rbrace$$

Formally:
- $L \in DSPACE(f)$ if there exists a deterministic TM $M$ such that:
  - On any input $x$, $M$ uses at most $cf(|x|)$ tape cells for some constant $c$.
  - $x \in L$ if and only if $M$ accepts $x$.



## Intuition
Deterministic, space-bounded computation: the machine must work within tight memory limits based on $f(n)$.

## Related
- [[NSPACE(f)]]
- [[DTIME(f)]]
- [[L (complexity class)]]
