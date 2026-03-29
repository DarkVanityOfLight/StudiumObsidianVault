```java
while (true) {
    ldecision = Decide();

    if (ldecision == NONE) {
        return SATISFIABLE;
    }

    tau = Simplify(tau U { ldecision = TRUE }, F);

    while (exists clause C in F that is falsified under tau) {
        Cconflict = Analyze(C, tau);

        if (Cconflict == EMPTY_CLAUSE) {
            return UNSATISFIABLE;
        }

        F = F U { Cconflict };

        tau = BackTrack(tau, Cconflict);

        tau = Simplify(tau, F);
    }
}
```



## Decision Levels
The solver assigns [literals](AlgoSAT/Literal.md) in sequence, forming a _trail_ $\tau$.
Each decision introduces a new decision level: if $\ell$ is the i-th decision literal denote $lev(\ell) = i$. All literals propagate from the decision receive the same level.

## Restarts
To avoid getting stuck locally, we do frequent restarts, following for example the [Luby Sequence](Luby%20Sequence.md).
To avoid loosing to much progress on these restarts, we might use [Phase Saving](Phase%20Saving.md).

## Choosing Variables
When splitting, we want to know which variable to assign, next. A good solution is to branch on variables that are "active" that means, they are often participating in conflicts, this can be done by using [VSIDS](VSIDS.md).


