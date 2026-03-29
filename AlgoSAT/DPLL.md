Using [Variable Elimination](Variable%20Elimination.md) we can obtain a complete Algorithm.

If both $x := \top$ and $x := \bot$ fail, then some $A_i$ and some $B_j$ are false, contradiction that all $A_i \lor B_j$ are true.

```
function DPLL(tau, F):

    tau_prime := Simplify(tau, F)

    // Check if all clauses are satisfied
    if F is satisfied under tau_prime then
        return SAT

    // Check if some clause is violated
    if F contains an empty clause under tau_prime then
        return UNSAT

    // Pick a branching literal
    l := Decide(tau_prime, F)

    // Branch: try l = true
    if DPLL(tau_prime union {l = true}, F) == SAT then
        return SAT

    // Otherwise try l = false
    return DPLL(tau_prime union {l = false}, F)
```

