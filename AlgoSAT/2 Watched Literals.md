[Clauses](Clause.md) maintain exactly _two watched literals_ to detect when the clause may become unit or conflicting.

Idea: instead of checking all [literals](AlgoSAT/Literal.md) of a clause on every [assignment](Assignment.md), we only track _two positions_ that gurantee we notice when the clause gets close to being falsified.

Each clause $C = (\ell_1 \lor \dots \lor \ell_k)$ stores two indices $w_1, w_2$, as long as at least one watch literal is unassigned or satisfied, the clause needs no further attention. When a watched literal becomes false, we try to move the watch to another non-false literal. If no such literal exists, the clause is either [unit](Unit%20Propagation.md) or _conflicting_.

We only need to examine a clause when both
1. A watch pointer gets falsified
2. the other one is not satisfied

While backjumping, we just unassign variables. When assigning variables, we find relevant clauses with the watch pointers.

