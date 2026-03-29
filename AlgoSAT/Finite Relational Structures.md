[Ehrenfeucht-Fraisse Game](Ehrenfeucht-Fraisse%20Game.md)
A [relation](Relation.md) of arity $r$ on a [set](Mengen.md) $A$ is a subset of $R\subset A^r$.

A finite relational structure is a tuple $(A, R_1, \dots, R_t)$ consisting of a finite set $A$ and a sequence of relations $R_1, \dots, R_t$ on $A$.

For relational structures $(A, R_1, \dots, R_t)$ and $(B, Q_1, \dots, Q_t)$ assume that $R_i$ and $Q_i$ have the same arity.

Then, an isomorphism $\varphi: A\to B$ is a bijection where
$$\forall i \in \{1, \dots, t\}. (a_1, \dots, a_{ar(R_i)}) \in R_i \iff (a_1^\varphi, \dots, a^\varphi_{ar(R_i)}) \in Q_i$$

> The isomorphism problem for finite relational structures is graph isomorphism complete.