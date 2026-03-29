```
for i in 1 to MAX_TRIES do
	α := random initial assignment
	for j in 1 to MAX_STEPS do
		if α satisfies Γ then
			return satisfiable
		α := flip (α)
return unknown
```

There are different types of flips:
- Free flips do not decrease the number of satisfied clauses
- Random flips are preformed regardless of effect
- Heuristic flips choose variables that leads to the "most improvement"

## Weight Transfer

All clauses have a weight. We pick the variable that reduces the falsified weight the most. If there is no weight-reducing variable, we modify the weights.

[Clauses](Clause.md) are _neighboring_ iff they share a [literal](AlgoSAT/Literal.md). We transfer weight between neighbors:
- we transfer weight from satisfied to falsified clauses
- from highest weight satisfied neighboring clause.

