When naively transforming from [Negation Normal Form](AlgoSAT/Negation%20Normal%20Form.md) into CNF, we get an exponential blowup on the formula size.

We can use Tseitins Transformation to convert a [Formula](Formula.md) $F$ into an [Equisatisfiable](Equisatisfiable.md) formula in CNF, linear in the size of $F$.


The key idea is to introduce auxiliary variables to represent subformulas and define those variables using CNF clauses.

We first convert the formula into NNF
and then generate the definitions from left to right:
- OR definition: 
  $$d \leftrightarrow x_1 \lor x_2 \lor \dots \lor x_k \equiv (x_1 \lor x_2 \lor \dots \lor x_k \lor \overline d) \land (\overline x_1 \lor d) \land (\overline x_2 \lor d) \land \dots \land (\overline x_k \lor d)$$
- AND definition:
  $$d \leftrightarrow x_1 \land x_2 \land \dots \land x_k \equiv (\overline x_1 \lor \overline x_2 \lor \dots \lor \overline x_k \lor d) \land (x_1 \lor \overline d) \land (x_2 \lor \overline d) \land \dots \land (x_k \lor \overline d)$$

