A quantified boolean formula is a [formula](Formula.md) together with quantifiers:

$$\forall y\exists x.(x \lor \overline y) \land (\overline x \lor y)$$

QSAT can be interpreted as a two player game, with player 1 choosing the existential variables and player 2 the universal ones.


We assume the formula to be in Prenex Conjunctive Normal form, that is we have all quantifiers at the front, followed by a quantifier free CNF.



A simple algorithm to solve, would be to split on each quantified variable, ensuring both branches result in true for universal variables and at least one for existential variables.

A [clause](Clause.md) $C$ is called _unit_ iff $C$ contains exactly one existential literal and the universal literals of $C$ are to the right of the existential literal in the prefix, then the existential literal in the unit clause is called unit literal.

If we have a unit literal $l$, we can remove all clauses containing $l$ and remove all occurrences of $\overline l$.

A literal $l$ is called _pure_ in a formula $\varphi$ iff
- $l$ occurs in $\varphi$
- the complement of $l$ $\overline l$ does not occur in $\varphi$.
We can remove a pure literal by, removing all clauses with $l$ if $l$ is existentially quantified, or removing all occurrences of $l$ if it is universally quantified.

## Universal Reduction

Let $\Pi. \psi$ be a QBF in PCNF and $C \in \psi$, let $l\in C$ be a universally quantified literal, and for all $k\in C$ where $k$ is existentially quantified are to the left of $l$ in $\Pi$, then we may remove $l$ from $C$. $C\setminus \{l\}$ is called the _universal reduct_ of $C$.

## Resolution

Let $C_1, C_2$, be clauses with existential literal $l\in C_1$ and $\overline l\in C_2$
1. Tenatice Q-resolvent $C_1 \bowtie C_2 := (UR(C_1) \cup UR(C_2)) \setminus \{l, \overline l\}$.
2. If $\{x, \overline x\} \subseteq C_1 \bowtie C_2$ then no Q-resolvent exists.
3. Otherwise, Q-resolvent $C := C_1 \bowtie C_2$


## Quantified Blocked Clause

An existential literal $l$ in clause $C$ of a QBF blocks $C$ with respect to $\Pi.\varphi$ if for every clause $D \in F_{\overline l}$, there exists a literal $k\not = l$ with $k \le_\Pi l$ such that $k\in C$ and $\overline k\in D$.

A clause is blocked if it contains a literal that blocks it.

