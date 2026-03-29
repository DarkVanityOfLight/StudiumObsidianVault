An _autarky_ is a partial [Assignment](Assignment.md) that satisfies all clauses that are touched by the assignment:
- A [Pure Literal](Pure%20Literal.md) is an autarky
- A satisfying assignment is an autarky
- Removing clauses that are satisfied by an autarky results in an [Equisatisfiable](Equisatisfiable.md) formula
- For any autarky $\alpha$ it holds that $\alpha\circ F\subseteq F$


Let $\alpha$ be an autarky for [Formula](Formula.md) $F$. Then $F$ and $\alpha \circ F$ are equisatisifiable:

If $F$ is satisfiable, then since $\alpha\circ F \subseteq F$ we know that $\alpha\circ F$ is satisfiable.

Conversely, suppose $\alpha\circ F$ is satisfiable and let $\alpha_1$ be an assignment that satisfies $\alpha\circ F$. We can assume $\alpha_1$ only assigns values to the variables of $\alpha\circ F$, which are distinct from the variables of $\alpha$. Then the assignment $\alpha_2 := \alpha \cup \alpha_1$ satisfies $F$.



