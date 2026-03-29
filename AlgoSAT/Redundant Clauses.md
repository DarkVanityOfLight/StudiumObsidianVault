A [clause](Clause.md) $C \not\in F$ is _redundant_ with respect to $F$ if adding it to the formula preserves satisfiability.

For an unsatisfiable [formula](Formula.md), all clauses can be added, including the empty clause.

A clause $C \in F$ is _redundant_ with respect to $F$ if removing it from the formula preserves unsatisfiability, for satisfiable formulas, all clauses can be removed.

## Tautology
A clause $C$ is a tautology if it contains two complementary [literals](AlgoSAT/Literal.md) $x$ and $\overline x$.

## Subsumption
Clause $C$ subsumes clause $D$ iff $C \subset D$.

This can be either done by a simple forward search, or by backward subsumption.

For each 
```
for each clause C in formula F do
	pick a literal x in C with minmal |Fx|
	for all clauses D in Fx
		if s(C) does not bitwise imply s(D) continue
		if C ⊂ D remove D
```

To speed up the $\subset$ test we can build a $k$ bit hash table
