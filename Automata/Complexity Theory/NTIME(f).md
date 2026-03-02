## Definition
$NTIME(f)$ is the class of languages that can be decided by a nondeterministic Turing Machine within $O(f(n))$ steps.

>$$NTIME(f) = \lbrace \text{languages accepted by nondeterministic, $f$-time bounded TMs} \rbrace$$

Formally:
- $L \in NTIME(f)$ if there exists a nondeterministic TM $M$ such that:
  - For all inputs $x$, there is some accepting computation path of $M$ of length at most $cf(|x|)$ (for some constant $c$) if $x \in L$.
  - If $x \notin L$, all computation paths reject.



## Intuition
Nondeterministic, time-bounded computation: the machine can "guess" solutions within time $f(n)$.

## Related
- [[DTIME(f)]]
- [[P]]
- [[NP]]
- [[NSPACE(f)]]
