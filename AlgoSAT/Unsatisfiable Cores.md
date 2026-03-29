Given an _unsatisfiable_ [formula](Formula.md) $F$, a subset $F' \subseteq F$ is an _unsatisfiable core_ of $F$ if $F'$ is itself unsatisfiable.

An unsatisfiable core $F' \subset F$ is _minimal_ iff for every [clause](Clause.md) $C\in F'$, the set $F'\setminus\{ C \}$ is satisfiable


We want to extract a minimal unsatisfiable core from a formula, but the cost of doing this might be high.

