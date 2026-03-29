
- [DPLL](Logik/DPLL.md) Aims at finding a small search-tree by selecting effective splitting variables. This is effective on small hard formulas, but expensive.
- [Local Search](Local%20Search.md): given a full assignment for a [formula](Formula.md) $F$, we flip the truth values of variables until we satisfy $F$, this can quickly find solutions for hard formulas but cannot prove unsatisfiability
- [CDCL - Conflict Driven Clause Learning](CDCL%20-%20Conflict%20Driven%20Clause%20Learning.md) makes fast decisions and converts conflicts into learned clauses, it is effective on large easy formulas but hard to parallelize.

