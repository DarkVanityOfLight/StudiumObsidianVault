We can explicitly check for the redundance of clauses and literals.

Check if $C\in F$ is [redundant](Redundant%20Clauses.md):
- Removal $C\in F$ preserves unsatisfiability of $F$
- Assign all $x\in C$ to false and check for a conflict in $F\setminus\{C\}$


Check if $x\in C$ is redundant:
- Removal of $x\in C$ preserves satisfiability of $F$
- Assign all $x' \in C\setminus \{x\}$ to false and check for a conflict in $F$

