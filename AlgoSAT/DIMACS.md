The DIMACS format for SAT solvers has three types of line:

- _header_ `p cnf n m` in which $n$ denotes the highest variable index and $m$ the number of [Clauses](Clause.md)
- _clauses_ A sequence of integers ending with $0$
- _comments_ any line starting with `c`

The solution line of a SAT solver starts with `s`
- `s SATISFIABLE` The formula is satisfiable
- `s UNSATISFIABLE`
- `s UNKNOWN`

In case the formula is satisfiable, the solver emits a certificate
- lines starting with `v` 
- a list of integers ending with `0`

In case the formula is unsatisfiable, then most solvers support emitting a proof of unsatisfiability to a separate file.

