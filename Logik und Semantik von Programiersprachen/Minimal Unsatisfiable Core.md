

Given a set $S$ of atoms in [theory](Theorien%20der%20ersten%20Stufe.md) $T$ such that

$$\bigwedge_{t\in S} t$$
is unsatisfiable, an __Unsatisfiable Core__ is any $M \subseteq S$ such that

$$\bigwedge_{t\in M} t$$
is unsatisfiable. It is minimum if no proper subset is an unsatisfiable core.



## Finding MUCs

Given a solver $A$ for $T$-conjunctive theory and an $T$ unsat set $S$:

1. Set $S' := \emptyset$
2. If $S = S'$, output $S'$
3. Pick an arbitrary $x\in S\setminus S'$
4. Run $A$ on $S\setminus\lbrace x\rbrace$
5. If (4) is sat, set $S' := S' \cup \lbrace x\rbrace$
6. If (4) is unsat, set $S := S\setminus \lbrace x\rbrace$
7. go to (2)

This will discover a MUC in a linear number of calls to $A$


